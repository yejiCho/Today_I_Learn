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

## 까먹어서 다시정리,,,

# Optional 클래스

- java.util.Optional<T> 클래스

```

Optional<T> 클래스는 Integer나 Double 클래스 처럼 'T'타입의 객체를 포장해주는 래퍼 클래스(Wrapper Class)입니다.
따라서 Optional 인스턴스는 모든 타입의 참조변수를 저장할 수 있습니다.

이러한 Optional 객체를 사용하면 예상치 못한 NullPointerException 예외를 제고오디는 메소드로 간단히 회피할 수 있습니다.
즉, 복잡한 조건문 없이도 널(null)값으로 인해 발생하는 예외를 처리할 수 있게 됩니다.

```

- Optional 객체의 생성

```
of() 메소드나 ofNullable() 메소드를 사용하여 Optional객체를 생성할 수 있습니다.

of() 메소드는 null이 아닌 명시된 값을 가지는 Optional객체를 반환합니다.
만약 of()메소드를 통해 생성된 Optional객체에 null이 저장되면 NullPointerException예외가 발생합니다.

따라서 만약 참조 변수의 값이 만에 하나 null이 될 가능성이 있다면, ofNullable()메소드를 사용하여 Optional 객체를 생성하는 것이 좋습니다.
ofNullable()메소드는 명시된 값이 null이 아니면 명시된 값을 가지는 Optional객체를 반환하며, 명시된 값이 null이면 비어있는 Optional 객체를 반환합니다.

```

```java

Optional<String> opt = Optional.ofNullable("자바 Optional 객체");
System.out.println(opt.get());

```

- [java @Optional](http://www.tcpschool.com/java/java_stream_optional)