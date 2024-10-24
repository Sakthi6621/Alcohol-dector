#define Motor 4
#include <Wire.h> //library that help to communicate with I2C
#include <LiquidCrystal_I2C.h> 
LiquidCrystal_I2C lcd(0x27, 16, 2);
int val = 0;
void setup()
{
  pinMode(A0, INPUT); //declare A0 as input pin
  lcd.init(); // initialize the LCD
  lcd.backlight(); //turn on the backlight
  lcd.clear(); //clear the LCD display
  Serial.begin(9600); //start serial monitor
}

void loop()
{
   val = analogRead(A0); //read the analog input from pin A0


 if ( val > 200 ) {
 tone(3,1000);      //activate buzzer at pin 3
     digitalWrite(Motor, LOW);
      lcd.setCursor(0,0);  //set cursor LCD
      lcd.print("Driver drunken ");
    lcd.setCursor(0,1);
      lcd.print("Engin OFF");
   }

   else{
    noTone(3);
        digitalWrite(Motor, HIGH);
     lcd.setCursor(0,0); //Set the cursor position
     lcd.print("Alcohol Value: "); // Start display on LCD
     lcd.setCursor(0,1);
      lcd.print(val);
     lcd.print("  Engin ON");
         delay(100);
        lcd.clear(); //clear LCD screen 
      Serial.println(val); //print val on serial monitor
   }
}
