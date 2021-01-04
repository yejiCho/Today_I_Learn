# file.getInputStream, file.outputstream

## File.getInputStream

```java

InputStream is = file.getInputStream();

// 선언시 is에는 BLOB 객체가 담긴다.
// BLOB는 주로 멀티미디어에 관함 객체이다.

```

## FileOutputStream

읽어들인 blob객체를 파일로 생성하고 싶을 때 사용하는 것

```java

FileOutputStream fos = new FileOutputStream(
    "c:/tmp/" + file.getOriginalFileName() + new Date()
);

// 위와 같은 방식으로 생성하며 괄호 안에 들어가는 매개변수는 생성할 파일의 경로 및 이름이다.
// new Date()를 붙여주는 이유는 중복 파일이 덮어쓰기 되는 것을 방지하기 위해서이다.

```


## InputStream.read() & fileOutputStream.write

> inputStream.read 메소드는 buffer를 인자로 받아 해당 buffer size만큼 byte를 읽는다.



- [file.input, outputstream](https://42kchoi.tistory.com/131)