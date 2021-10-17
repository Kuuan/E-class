# LCD顯示"Hello" + 你的英文名字 (e.g., "Hello Horace")

# 電路圖
![image](https://user-images.githubusercontent.com/89329117/137610288-aeb99ef4-c16a-4e86-a0e0-ddd7ff754305.png)

#CODE
````c
// include the library code:
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

void setup() {
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.
  lcd.print("Hello, Kuuan!");
}

void loop() {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 1);
  // print the number of seconds since reset:
  lcd.print(millis() /100);
}
````
