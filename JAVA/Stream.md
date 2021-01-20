# Stream

```
stream은 자바8부터 추가된 컬렉션의 저장요소를 하나씩 참조해서 람다식으로 처리할 수 있도록 해주는 반복자입니다.
Iterator와 비슷한 역할을 하지만 람다식으로 요소 처리 코드를 제공하여 코드가 좀 더 간결하게 할 수 있다는 점과 내부 반복자를 사용하므로
병렬처리가 쉽다는 점에서 차이점이 있습니다.

```

## Iterator과 Stream의 코드 비교

```java

ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
Iterator<Integer> iter = list.iterator();

while(iter.hasNext()){
    int num = iter.next();
    System.out.println("값 : " + num);
}

ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
Stream<Integer> stream = list.stream();
stream.forEach(num -> System.out.println("값 : "+num));

```

## collect

> Collect는 명백하게 유용한 터미널 오퍼레이션이다. 스트림의 각 엘리먼트를 다른 종류의 결과로 만들기 위해 트랜스폼 하기 위해 사용된다. Collect는 4개의 다른 오퍼레이션으로 구성된 collector를 적용할 수 있다. :supplier, accumulator, combiner, finisher

```java

List<Person> filteredPersons = persons.stream().filter(person -> person.name.startsWith("P")).collect(Collectors.toList());

System.out.println(filteredPersons);

```

```
[Person{name='Peter',age=23},Person{name='Pamela', age=23}]

```

- 나이로 모든 사람들을 그룹핑

```java

Map<Integer, List<Person>> personsByAge = persons.stream().collect(Collectors.groupingBy(person -> person.age));

personsByAge.forEach((age,personGroup)->{
    System.out.println(String.format("age: %d, persons: %d",age,personGroup));
})

```

```
age: 18, persons: [Person{name='MAX', age=18}]
age: 23, persons: [Person{name='Peter', age=23}, Person{name='Pamela',age=23}]
age: 12, persons: [Person{name='David', age=12}]

```