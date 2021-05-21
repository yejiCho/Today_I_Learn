# Split

```java

String[] arStr = "ABC DEF".split(" ");

// space 한칸
String[] arStr = "ABC DEF".split("\\s");

// 가변적 공백1개 이상인 경우
String[] arStr = "ABC    DEF".split("\\s+");

// enter일 경우
String[] arStr = "ABC
                  DEF".split("\\r?\\n");

```