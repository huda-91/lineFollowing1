package Noura_Huda;

import lejos.nxt.*; 

public class yellowDetector { 
	
public static void main(String [] args) { 
int blackID = 7 , yellowID=3 ; 
int readColor = 0; // to store the ID of the color
int forward = 1, stop = 3; // set the mode ,1=forward, 2=backward, 3=stop, 4=float 
int power = 80; //set speed to 80
int counter=0; // counter to count the yellow objects


//Create Color Sensor instance and bind it to port 1
 ColorSensor cs=new ColorSensor(SensorPort.S1);
 readColor = cs.getColorID();
 
while (Button.readButtons() == 0) {
	
if (readColor == blackID )  // in case of black background turn left
   
   { 
     MotorPort.C.controlMotor(0,stop); 
     MotorPort.B.controlMotor(power, forward); 
   }

 else if (readColor==yellowID)//if color sensor reads the yellow color while following the black line
	 
   {
     MotorPort.C.controlMotor(0,stop); 
     MotorPort.B.controlMotor(power, forward);
     Sound.twoBeeps();
     counter++;
     LCD.refresh();
     LCD.drawString("Number of yellow  ",0,0);
     LCD.drawInt(counter, 0, 1);
   } 
 
else // in case of white background turn right
	
  { 
    MotorPort.B.controlMotor(0,stop); 
    MotorPort.C.controlMotor(power, forward); 
  } 

readColor = cs.getColorID(); //updating readColor


       }//while
    }//main 
 }//class
