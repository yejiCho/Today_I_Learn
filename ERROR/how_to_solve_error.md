# java.lang.ClassCastException: java.math.BigInteger cannot be cast to java.lang.Integer

- IN case

```
ArrayList<Integer>에서 data를 가져와 변수에 저장했을 경우,
DB에서 map으로 받아서 가져올 경우에 종종 발생한다.
```

```
List<Integer> totalCount = Service;
int test = totalCount.get(0);

--> BigInteger error
```

- Solve

```java

int test = totalCount.get(0);

int test = Integer.parseInt(String.valueOf(totalCount.get(0)));

```