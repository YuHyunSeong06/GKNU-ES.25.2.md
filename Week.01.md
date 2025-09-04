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
```java
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
##### pinMode(pin, mode) : 특정한 핀을 입력으로 쓸지 출력으로 쓸지 설정하는 함수
#####         - pin: 설정하려는 핀의 번호
#####         - mode : OUTPUT(출력), INPUT(입력), INPUT_PULLUP(내부의 풀업저항 사용) 중 원하는 모드 설정
##### digitalWrite(핀번호, 값) : 주어진 핀번호에 대해 값을 기록
#### 2번 LED 깜빡이는 코드
```c
void setup(){
  pinMode(13,OUTPUT); // pinMode
}

void loop(){
  digitalWrite(13,HIGH);
  delay(250);
  digitalWrite(13,LOW);
  delayy(250);
}
```
#### 1번 LED 깜빡이는 코드
```c
void setup(){
  pinMode(13,OUTPUT); // pinMode
}

void loop(){
  digitalWrite(13,HIGH);
  delay(250);
  digitalWrite(13,LOW);
  delayy(250);
}
```
#### 뒤를 부탁한다 수경티비비
```c
void setup(){
  pinMode(13,OUTPUT);
  Serial.begin(9600);
}

void loop(){
  int a = Serial.read();

  if(a=='1') digitalWrite(13,HIGH);
  if(a=='0') degitalWrite(13,LOW);
}
```
##### Serial Monitor를 통해 아두이노를 조종할 수 있다.
####
```java
import processing.serial.*;
Serial p;

void setup(){
	p=new Serial(this, "COM3",9600);
}

void draw(){
}
void keyPressed(){
	p.write(key);
}
```
