# Optional

- null 관련 문제

```
런타임에 NPE(NullPointerException)라는 예외 발생
NPE 방어를 위해서 들어간 Null 체크 로직때문에 코드가독성과 유지보수성이 떨어짐
```

- Optional이란?

```
존재할 수도 있지만 안 할수도 있는 객체, 즉 null이 될 수도 있는 객체를 감싸고 있는
일종의 래퍼 클래스입니다.
원소가 없거나 최대 하나밖에 없는 Collection이나 Stream
```

- 효과

```
NPE를 유발할 수 있는 null을 직접 다루지 않아도됨
null체크를 직접하지 않아도됨
명시적으로 해당 변수가 null일 수도 있다는 가능성을 표현할 수 있습니다.
```


- [Optional원리와이해](https://www.daleseo.com/java8-optional-before/)

## void

```
void의 역할은 return되는 타입이 없음을 의미
즉, 아무것도 리턴하지 않음을 선언
```

```java

public void test(){
    siteurl = 'www';
}

public String getUrl(){
    return 'teete';
}

```