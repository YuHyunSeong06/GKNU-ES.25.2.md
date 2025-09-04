## 임베디드 시스템
##### Arduino IDE 와 Processing 다운로드
###### 25.09.02 첫번째 수업
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
```
