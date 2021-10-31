# 實作6: 4X4鍵盤 + LCD 顯示器

## 電路圖
![image](https://user-images.githubusercontent.com/89329117/139566790-1dec6088-8186-400a-9498-2e4ebf18baff.png)
## CODE
````c
#include <Keypad.h>
#include <LiquidCrystal.h>

LiquidCrystal lcd(5, 4, 3, 2, A4, A5);

const byte ROWS = 4; //four rows
const byte COLS = 4; //three columns
char keys[ROWS][COLS] = {
  {'1','2','3','A'},
  {'4','5','6','B'},
  {'7','8','9','C'},
  {'*','0','#','D'}
};
byte rowPins[ROWS] = {A0, A1, 11, 10}; //connect to the row pinouts of the keypad
byte colPins[COLS] = {9, 8, 7, 6}; //connect to the column pinouts of the keypad
int LCDCol = 0;
int LCDRow = 0;

Keypad keypad = Keypad( makeKeymap(keys), rowPins, colPins, ROWS, COLS );


void setup(){
   Serial.begin(9600);
   lcd.begin(16, 2);
   lcd.setCursor(LCDCol, LCDRow);
   }
  
void loop(){
  char key = keypad.getKey();
  
  if (key){
    
    Serial.println(key);
           
    
    if ( LCDCol > 15  )
    {   
     ++LCDRow; // Move to the 2nd row
      
      if (LCDRow>1)
      { LCDRow=0; LCDCol = 0 ;  lcd.clear(); } // 清除後並回第一行
   
    LCDCol = 0 ;
    }
         
    lcd.setCursor (LCDCol, LCDRow); 
    
       lcd.print(key);
    
    ++LCDCol;
    
  }
}


````
