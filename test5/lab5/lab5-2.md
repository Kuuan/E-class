# 5-2 LCD顯示溫度感應器的溫度;若溫度<0 藍LED亮; 若溫度<32 綠LED亮; 若大於32度, 紅色LED亮

## 電路圖
![01](https://user-images.githubusercontent.com/89329117/138580091-9c32e0b1-42a0-4124-8a94-cc1dda04aeb7.jpg)

## code
````c
#include <LiquidCrystal.h>

LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

int GLED = 6;
int RLED = 8;
int BLED = 7;

void LED(int RH,int GH,int BH)
{
  digitalWrite(RLED, RH);
  digitalWrite(GLED, GH);
  digitalWrite(BLED, BH);
}

void setup() {
  lcd.begin(16, 2);
  Serial.begin(9600);	
  pinMode(A1, INPUT); // Read analog voltage level (2^10)
  
  digitalWrite(RLED, OUTPUT);
  digitalWrite(GLED, OUTPUT);
  digitalWrite(BLED, OUTPUT);

}

void loop() {
  int reading = analogRead(A1);  // read analog level level (2^10)
  lcd.setCursor(0,0);  
  lcd.print("TMP Sensor Demo");

float voltage = (reading/1024.0)*5.0;
  
float tempC=(voltage - 0.5)*100.0;
  lcd.setCursor(0,1);
  lcd.print("Tmp:");
  lcd.print(tempC);
  lcd.print(" C");
  delay(500);
  lcd.clear();
  Serial.println(reading);
  Serial.println(voltage);  
  
  if(tempC<0){
    LED(0,0,1);
  }
  else if(tempC<32){
    LED(0,1,0);
  }
  else{
    LED(1,0,0);
  }
 
}
````
