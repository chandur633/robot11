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
