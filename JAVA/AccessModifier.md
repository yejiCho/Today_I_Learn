# 접근제어자 (AccessModifier)

1. private
2. default
3. protected
4. public

private -> default -> protected -> public 순으로 보다 많은 접근을 허용한다.

## private

접근제어자가 private으로 설정되었다면 private이 붙은 변수, 메소드는 해당 클래스에서만 접근 가능

```java

public class AccessModifier{
    private String secret;
    private String getSecret(){
        return this.secret;
    }
}

```
위 예제의 secret변수와 getScret메소드는 오직 AccessModifier 클래스에서만 접근이 가능하고
다른 클래스에서는 접근이 불가능하다.


## default

접근제어자를 별도로 설정하지 않는다면 접근제어자가 없는 변수, 메소드는 default 접근제어자가 되어 해당 패키지 내에서만 접근이 가능

```java
// HouseKim.java

package jump2java.house;

public class HouseKim {
    String lastname = "Kim";
}

```

```java
// HousePark.java

package jump2java.house;

public class HousePark{
    String lastname = "park";

    public static void main(String[] args){
        House Kim = new HouseKim();
        System.out.println(kim.lastname); 
    }
}

```

## protected

접근제어자가 protected로 설정되었다면 protected가 붙은 변수, 메소드 동일패키지내의 클래스 또는 해당 클래스를 상속받은 외부 패키지의 클래스에서 접근이 가능하다.

```java
// HousePark.java
package jump2java.house;

public class HousePark {
    protected String lastname = "park";
}

// EungYongPark.java
package jump2java.house.person;

import house.HousePark;

public class EungYongPark extends HousePark{
    public static void main(String[] args){
        EungYongPark eyp = new EungYongPark();
        System.out.println(eyp.lastname);
    }
}

```

```
HousePark클래스를 상속받은 EungYongPark이라는 클래스의 패키지는 jump2java.house.person으로 HousePark의 패키지인 jump2java.house와 다르지만 HousePark의 lastname 변수가 protected로 설정되었기 때문에 eyp.lastname과 같은 접근이 가능하다.

만약 lastname의 접근제어자가 protected 가 아닌 default 접근제어자였다면 eyp.lastname 문장은 컴파일 에러를 유발 할 것이다.

```

## public 

접근제어자가 public으로 설정되었다면 public 접근제어자가 붙은 변수, 메소드는 어떤 클래스 에서라도 접근이 가능하다.


- [java 접근제어자](https://wikidocs.net/232)

- [메소드 오버라이딩,오버로딩](https://wikidocs.net/280)