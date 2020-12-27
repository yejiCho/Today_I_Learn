# Stream

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