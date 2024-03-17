# GasDetection_Using_Aurdino
A gas detection system using Arduino is an electronic device designed to detect the presence of specific gases in the surrounding environment. It employs various sensors to monitor gas levels and alerts users when gas concentrations exceed predefined thresholds, helping to prevent potential hazards such as leaks or exposure to harmful gases.
WORKING:
•	Connect the LCD with the 5V of VCC to the breadboard, Second Pin connect gng pin to the breadboard wire.
•	Now connect LCD ground pin to ground, Vcc pin connect to Vcc, also connect ground pin connect to ground.
•	Vcc pin connect to led here is a led anode and led cathode, resistance connect to LED anode pin and change the value of resistance and change value of resistance 330 Ohm and connect to VCC.


Code:
Gas Sensor Detect: 
#include <LiquidCrystal.h> 
LiquidCrystal lcd(8,7,6,5,4,3); 
int LDR_VAL = 0; 
void setup() 
{ 
 pinMode(A0,INPUT); 
 Serial.begin(9600); 
 lcd.begin(16,2); 
 lcd.setCursor(0,0); 
 lcd.print("GAS SENSOR");  
} 
void loop() 
{ 
 LDR_VAL = analogRead(A0); 
 Serial.println(LDR_VAL);  
 lcd.setCursor(0,1);
 lcd.print(LDR_VAL);  
 delay(10); 
}  
Gas Detected/ Gas Not-Detected: 
#include <LiquidCrystal.h> 
LiquidCrystal lcd(8,7,6,5,4,3); 
int LDR_VAL = 0; 
void setup() 
{ 
pinMode(A0,INPUT); 
Serial.begin(9600); 
lcd.begin(16,2); 
lcd.setCursor(0,0); 
lcd.print("GAS SENSOR")  
} 
void loop() 
{ 
 LDR_VAL = analogRead(A0);  Serial.println(LDR_VAL); 
 if (LDR_VAL > 500) 
 { 
 lcd.setCursor (0,1); 
 lcd.print ("GAS DETECTED");  } 
 else 
 { 
 lcd.setCursor(0,1); 
 lcd.print ("GAS NOT DETECT");  }  
 delay(10);
} 



