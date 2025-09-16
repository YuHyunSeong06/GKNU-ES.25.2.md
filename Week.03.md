## MIT App Inventor 와 Processing 설치

##### 아두이노 테스트
```c
void setup(){
  Serial.begin(9600);
  pinMode(13, OUTPUT);
}

void loop(){
  if(Serial.available()>0){
    char a = Serial.read();
    if(a=='0') digitalWrite(13, LOW);
    if(a=='1') digitalWrite(13, HIGH);
  }
}
```
