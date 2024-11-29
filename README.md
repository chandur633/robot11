squarechallenge

#include<PRIZM.h>
PRIZM prizm;

void setup() {
  prizm.PrizmBegin();
  prizm.setMotorInvert(1,1);
}

void loop() {
  
  for(int x=0;x<=3;x++)
  {
    forward();
    rightturn();
    
  }
  prizm.PrizmEnd();
}
void forward(){
  prizm.setMotorPowers(50,50);
  delay(3000);
  prizm.setMotorPowers(125,125);
  delay(1000);
}
void rightturn(){
  prizm.setMotorPowers(100,-100);
  delay(600);
  prizm.setMotorPowers(125,125);
  delay(1000);
}




lightsensorchallenge

#include<PRIZM.h>
PRIZM prizm;
void setup() {
prizm.PrizmBegin();
prizm.setMotorInvert(1,1);
}
void loop() {
  if(prizm.readLineSensor(3)==0){
    prizm.setMotorPowers(35,35);
    
  }
  if(prizm.readLineSensor(3)==1){
    prizm.setMotorPowers(125,125);
    while(1){
      prizm.setRedLED(HIGH);
      delay(500);
      prizm.setRedLED(LOW);
      delay(500);
      
    }
  }
}





ultrasonicsensor


#include<PRIZM.h>
PRIZM prizm;
void setup() {
  prizm.PrizmBegin();
  prizm.setMotorInvert(1,1);
  
}
void loop() {
  if(prizm.readSonicSensorCM(4)>25)
  {
    prizm.setMotorPowers(50,50);
  
  }
  else
  {
    prizm.setMotorPowers(125,125);
  }
}





obstacleavoider


#include<PRIZM.h>
PRIZM prizm;
void setup() {
  prizm.PrizmBegin();
  prizm.setMotorInvert(1,1);
  
}
void loop() {
  if(prizm.readSonicSensorCM(4)>25)
  {
    prizm.setMotorPowers(50,50);
  
  }
  else
  {
    prizm.setMotorPowers(125,125);
  }
}





obstacleavoider(easycode)

#include<PRIZM.h>
PRIZM prizm;
void setup() {
  prizm.PrizmBegin();
  prizm.setMotorInvert(1,1);
  
}
void loop() {
  if(prizm.readSonicSensorCM(4)>25)
  {
    prizm.setMotorPowers(35,35);
    
  
  }
  else
  {
   prizm.setMotorPowers(-35,-35);
    delay(1000);
    
    prizm.setMotorPowers(75,125);
    delay(1000);
    
    
    
    
  }
}





lightultrasonic semsor

#include<PRIZM.h>
PRIZM prizm;
void setup(){
  prizm.PrizmBegin();
  prizm.setMotorInvert(1,1);
  
}
void loop(){
  if(prizm.readSonicSensorCM(4)>25){
    
  
    while(prizm.readLineSensor(3)==1){
    prizm.setMotorPowers(0,20);
    delay(100);
}
    while(prizm.readLineSensor(3)==0){
    prizm.setMotorPowers(20,0);
    delay(100);
  }
  }
  else{
    prizm.setMotorPowers(125,125);
    
  }
  
}
\





batterycapacity



#include<PRIZM.h>
PRIZM prizm;
void setup() {
Serial.begin(9600);
prizm.PrizmBegin();
}

void loop() {
prizm.setMotorPower(1,50);
float y=prizm.readBatteryVoltage();
Serial.print(y/100);
Serial.print(",");

delay(250);
float x=prizm.readMotorCurrent(1);
Serial.print(x);
Serial.print(",");
delay(250);
float r=x*y;
Serial.println(r);
}





3 power 


#include<PRIZM.h>
PRIZM prizm;
void setup() {
Serial.begin(9600);
prizm.PrizmBegin();
}
void loop() {
prizm.setMotorPower (1,50);
float x = prizm.readMotorCurrent(1);
float y = prizm.readBatteryVoltage();
Serial.print(x);
Serial.print(",");
Serial.print(y);
Serial.print(",");
float r=x*y;
Serial.println(r);
delay(250);







Volt Current 


#include<PRIZM.h>
PRIZM prizm;
void setup() {
Serial.begin(9600);
prizm.PrizmBegin();
prizm.setMotorInvert(2,1);
prizm.resetEncoder(1);
int b= 6550;
while(prizm.readEncoderCount(1)<b)
{
prizm.setMotorPowers(10,10);
int a = prizm.readMotorCurrent(2);
int x = prizm.readBatteryVoltage();
int y = prizm.readMotorCurrent(1);
int z = x*y;
Serial.printin(x);
Serial.println(y);
while(prizm.readEncoderCount(1)<b)
{
prizm.setMotorPowers (10,10);
int a = prizm.readMotorCurrent(2);
int x = prizm.readBatteryVoltage();
int y = prizm.readMotorCurrent(1);
int z = x*y:
Serial.println(x);
Serial.println(y);
Serial.println(z);
delay(250);
}
prizm.setMotorPowers (125,125);
}
void loop() {
}






(P1) TETRIC Encoder Challenge 



#include <PRIZm.h>
PRIZM prizm;
Void setup() {
prizm.prizmBegin();
prizm.setMotorInvert (2,1);
{
Strline (7858);
Iturn (1723);
Strline (1964);
Iturn (1723);
Strline (7858);
rturn (1723);
Strline (5893);
rturn (1723);
Strline (1964);
rturn (1723);
Strline (3928);
lturn (1723);
Strline (982);
Iturn (383);
Strline (3928);
rturn( ); 
Strline (3274);
rturn (478);
Strline (3928);
}
}

void strline (int encodercount)
{
prizm.resetEncoders();
while (prizm.redEncoderCount(1)<encoderCount)
{
prizm.setMotorPowers (50.50),
}
prizm.setMotorPowers (125, 125);
delay (1000);
}
void rturn (int encoderCount)
{
prizm.resetEncoders();
while (prizm.readEncoderCount(1)<encoderCount)
{
prizm.setMotorPowers (50.0);
 }
prizm.setMotorPowers (125, 125);
delay(1000);
}
Void lturn (int encodercount)
{
prizm.resetEncoders ();
while (prizm.readEncoderCount(2<encoderCount)
{
prizm.setMotorPowers (0.50);
}
prizm.setMotorPowers (125,125); 
delay (1000);
}
void Loop() {
}

