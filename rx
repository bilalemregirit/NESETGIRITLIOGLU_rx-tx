#include <SPI.h>
#include <nRF24L01.h>
#include <RF24.h>
#include <MPU6050_tockn.h>
#include <Wire.h>

RF24 radio(9, 10); // CE, CSN

const byte address[6] = "00001";

 struct  Alinan_veri {
  byte ch1;
  byte ch2; 
};

Alinan_veri alinan_veri;
MPU6050 mpu6050(Wire);

void setup()
{
  Serial.begin(9600);
   Wire.begin();
  
  radio.begin();
  radio.setAutoAck(false);
  radio.setDataRate(RF24_250KBPS);  
  radio.openReadingPipe(0, address);
  radio.setPALevel(RF24_PA_MIN);
  radio.startListening();
  pinMode(2,OUTPUT);
  pinMode(4,OUTPUT);

  //mpu6050.begin();
  //mpu6050.calcGyroOffsets(true);
  
}

void loop()
{
      // mpu6050.update();
      
if(radio.available() ){


    
    radio.read(&alinan_veri, sizeof(Alinan_veri));
    delay(20);
    Serial.println(alinan_veri.ch1);
    Serial.println(alinan_veri.ch2);
   
   /*(serial monitor)
    Serial.print("angleX : ");
    Serial.print(mpu6050.getAngleX());
    Serial.print("\tangleY : ");
    Serial.print(mpu6050.getAngleY());
    Serial.print("\tangleZ : ");
    Serial.println(mpu6050.getAngleZ());
   */    

   //------------EKRAN-İLETİM-----------------------(for nextion displays)
   /*
   int denemedeg = map(alinan_veri.ch1,0,50,270,360);
   Serial.print("z0.val="); 
   Serial.print(alinan_veri.ch1);
   Serial.write(0xff);
   Serial.write(0xff);
   Serial.write(0xff);
   */
   //------------EKRAN-İLETİM-----------------------
}

}
