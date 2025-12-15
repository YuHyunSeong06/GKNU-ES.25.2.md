### 4강
```cpp
// 아두이노에서 4번 핀을 GND와 점퍼선으로 스위치를 만든다.

void setup() {
  Serial.begin(9600);
  pinMode(4, INPUT_PULLUP);
}
void loop() {
  int a = digitalRead(4);
  Serial.println(a);
  delay(500);
}
```
```java
import processing.serial.*;
import processing.net.*;
Serial p;
Server s;
Client c;
void setup() {
  p = new Serial(this, "COM4", 9600);
}
```
```
[문항]

Q: 아두이노에서 데이터를 서버로 보내기 위해 사용하는 통신 방식은 무엇인가요?

A: 시리얼 통신

Q: 프로세싱에서 아두이노와 통신하기 위해 사용하는 라이브러리는 무엇인가요?

A: Serial

Q: 프로세싱에서 웹 서버를 생성하기 위해 사용하는 클래스는 무엇인가요?

A: Server

Q: 스마트폰 앱을 만들기 위해 사용한 도구는 무엇인가요?

A: 앱 인벤터(App Inventor)

Q: 프로세싱에서 클라이언트의 요청을 처리할 때, HTTP 응답 코드로 무엇을 사용하나요?

A: 200 OK
```

### 5강
