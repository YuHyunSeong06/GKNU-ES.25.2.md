## 임베디드 시스템
##### Arduino IDE 와 Processing 다운로드
###### 25.09.02 첫번째 수업
##### Arduino IDE로 코딩
```c
void setup(){
  pinMode(13, OUTPUT);
  Serial.begin(9600);
}

void loop(){
  if(Serial.available()>0){
    char a = Serial.read();
    if(a=='0') digitalWrite(13, LOW); // 0V
    if(a=='1') digitalWrite(13, HIGH);
  }
}
```
##### processing로 코딩
```c
import processing.serial.*;
Serial p;
void setup()
{
  size(200,200);
  p = new Serial(this, "COM3", 9600);
}

void draw(){
}

void key(){
  p.write(key);
}
```

###### 25.09.04 첫번째 수업
## 아두이노의 구성 및 코드
##### void 리턴값 x
##### setup() : 한 번만 돌아가는 함수
##### loop() : 반복되는 함수
##### 13번 붉은선 : 길이가 길다
##### gnd 검은선 : 길이가 짧다
##### 아두이노 그라운드는 3개
```c
void setup(){
  pinMode(13,OUTPUT); // pinMode
}

void loop(){
  digitalWrite(13,HIGH);
  delay(500);
  degitalWrite(13,LOW);
  delay(500);
}
```
