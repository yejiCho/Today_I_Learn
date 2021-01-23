# length(), length, size()

|함수|길이를 반환하는 데이터 타입|
|:--:|:--:|
|length|배열|
|length()|문자열(String Object)|
|size()|컬렉션 프레임워크 타입(ArrayList, ...)|


```

배열과 문자열은 immutable한 특징을 갖는다. 그리고 최상위 Collection의 하위 클래스는
immutable한 특징을 갖는다. 

그래서 'length'라는 것을 봤다면, 그건 constant(=immutable) 변수 일 것이다.
이와 반대일 때 "size"를 볼 수 있다.

```

- 문자열이 immutable하다?

immutable이란?

```

생성 후 변경 불가능한 객체를 의미한다.
immutable 클래스로는 String, Boolean, Integer, Float, Long등이 있다.

그런데 여기서 말하는 immutable이란 값 자체를 변경못한다는 게 아니라 heap메모리에서의
변경이 불가능하다는 것이다.

즉 String str = "a"; -> str = "b"; 로 값을 변경하는 것은 가능하지만,

str이 heap메모리에서 가리키는 주소값이 바뀌는 것이 아니다.

```

- Call by Reference & Call by Value