# Entity

```
엔티티란 한마디로 경량의 영속성 도메인 오브젝트입니다.

여기서 또 영속성이란 메모리영역이 아닌 물리 데이터 저장공간(database)에 저장되어 애플리케이션이 종료되더라도 데이터가 사라지지않고 남아있음을 의미

하나의 엔티티는 하나의 테이블!
```

## Entity의 제약조건

1. 반드시 클래스에 @Entity어노테이션이 정의되거나, XML에 작성해야함

```java

@Entity
public class Player{

}

```

2. 반드시 no-args(파라미터가 없는)생성자를 가지고 있어야 합니다.

```
파라미터가 있는 생성자를 가지고 있어도되지만, 이 경우 반드시 public 혹은 protected의 접근자를 가진 no-args생성자를 선언해주어야 합니다.

직접 정의한 생성자가 하나도 없다면, 따로 생성자를 작성할 필요는 없습니다.
```

3. 엔티티는 최상위 클래스이어야합니다.

enum이나 interface타입으로 정의해서는 안됩니다.

4. 엔티티클래스는 final이어서는 안됩니다.

메소드가 없거나 영속성 필드가 없는 경우에는 final로 선언은 가능

## 영속 가능한 타입

Entity는 기본적으로 아래와 같은 타입을 영속 필드로 가질 수 있습니다.

- 사용자 정의 클래스: Entity 클래스, MapperSuperClass, Embeddable클래스
- 자바 데이터 타입: 기본자료형, String, 래퍼클래스, Date, Math타입
- 다중값 타입: Collection, Array, Map
- 기타: enum, Serializable타입


- [Spring data-entity](https://chan180.tistory.com/167)

- [Spring saveAndFlush](https://happyer16.tistory.com/entry/Spring-jpa-save-saveAndFlush-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%95%8C%EA%B3%A0-%EC%93%B0%EA%B8%B0)

- [Spring saveAndFlush](https://ramees.tistory.com/36)