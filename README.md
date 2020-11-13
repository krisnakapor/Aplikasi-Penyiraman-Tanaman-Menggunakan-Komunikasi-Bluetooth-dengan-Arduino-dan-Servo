# Bluetooth-Arduino-Servo

```
#include<Servo.h>             //memanggil library servo

Servo myservo;
int pos = 0;
char data = 0;            
   
void setup() 
{
  myservo.attach(11);         //Mengatur Servo pada pin 11
  Serial.begin(9600);         //Mengatur data rate dalam bits per second (baud) untuk transmisi data serial
  pinMode(13, OUTPUT);        //Mengatur digital pin 13 sebagai output pin LED
}
void loop()
{
  if(Serial.available() > 0)  //Mengirim data ke arduino ketika menerima data dari bluetooth
  {
    data = Serial.read();                 
    if(data == 1){            
      digitalWrite(13, HIGH);
      myservo.write(180);      //Mengirim data ke servo untuk menggeser servo ke 90 derajat atau membuka aliran air
    }
    if(data == 0){
      digitalWrite(13, LOW);
      myservo.write(90);       //Mengirim data ke servo untuk menggeser servo ke 0 derajat atau menutup aliran air
    }
  }
}
```
#Bluetooth-Arduino-Servo
