## 아두이노

### 저항 계산법
##### nnn ohm 에서 저항의 계산법
##### 첫번쨰 띠는 10의 자리를 나타낸다.
##### 두번쨰 띠는 일의 자리를 나타낸다.
##### 세번째 띠는 10의 승 수를 나타낸다.
##### 네번째 띠는 정확도를 나타낸다.
##### 색상표 첫두때 마지막
##### 검 0 0   
##### 갈 1 10
##### 빨 2 100
##### 주 3 1000
##### 노 4 10000
##### 초 5
##### 파 6
##### 보 7
##### 회 8
##### 흰 9
##### 금 오차 및 곱하기때만
##### 은 마찬가지
##### ex) 330ohm 주주갈
##### ex) 10kohm 갈검주
```c
void setup() {
  Serial.begin(9600);
  pinMode(13,OUTPUT);
  pinMode(12,OUTPUT);
  pinMode(4, INPUT_PULLUP);
}
double th(int v) {
  double t; // http://en.wikipedia.org/wiki/Thermistor
  t = log(((10240000/v) - 10000));
  t = 1 /(0.001129148 + (0.000234125*t) + (0.0000000876741*t*t*t));
  t = t - 273.15; // 화씨를 섭씨로 바꾸어줌
  return t;
}
void loop() {
  int a = analogRead(A0);
  int b = analogRead(A1);
  int c = th(b);
  int p = digitalRead(4);
  Serial.print("Swtich: ");
  Serial.print(p);
  Serial.print("LIGHT: ");
  Serial.print(a);
  Serial.print(" TEMP: ");
  Serial.println(c);
  delay(500);
  if(Serial.available()>0){
    char d = Serial.read();
    if(d=='1') {
      digitalWrite(13, HIGH);
      digitalWrite(12, LOW);
    }
    if(d=='2') {
      digitalWrite(13, LOW);
      digitalWrite(12, HIGH);
    }if(d=='0') {
      digitalWrite(13, LOW);
      digitalWrite(12, LOW);
    }
  }
}
```
```java
import processing.serial.*;
import processing.net.*;
Serial p;
Server s;
Client c;
void setup() {
  p = new Serial(this, "COM3", 9600); // 주의1: 포트번호
  s = new Server(this, 12345);
}
String msg;
void draw() {
  if(p.available() > 0) {
    msg = p.readStringUntil('\n');
    if (msg != null) {
      msg = msg.trim();
      println(msg);
    }
  }
  c = s.available();
  if (c != null) {
    String g = c.readString();
    if (g != null && g.length() > 0) {
      g = g.substring(g.length() - 1);
      print(g);
      p.write(g);
      c.write("http://1.1 200 0K\r\n\r\n");
      if (msg != null) {
        c.write(msg);
      }
    }
    c.stop();
  }
}

```
