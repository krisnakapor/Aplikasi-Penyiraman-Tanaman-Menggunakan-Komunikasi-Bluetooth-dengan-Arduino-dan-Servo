# Android-Bluetooth-Control-Arduino-LED

This project Desigened for Arduino Bluetooth control HC-05 module from Android.

Arduino code for Hc-05 module 

```

char data = 0;               
void setup() 
{
  Serial.begin(9600);         //Sets the data rate in bits per second (baud) for serial data transmission
  pinMode(13, OUTPUT);        //Sets digital pin 13 as output pin
}
void loop()
{
  if(Serial.available() > 0)  // Send data only when you receive data:
  {
    data = Serial.read();             
          
    if(data == 1)            
      digitalWrite(13, HIGH);  
    else
      digitalWrite(13, LOW);   
  }                           
 
}
```

Coneection Method Arduino to HC-05 module

set pin HC-05 module Rx - Arduino Tx 

set pin HC-05 module TX - Arduino RX

set GCC-GCC and 5v-5V
