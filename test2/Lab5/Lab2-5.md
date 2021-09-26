# 實作2-5: 按下按鍵, Green LED亮 & Red LED滅; 放開按鍵, Green LED滅 & Red LED亮.

## 電路圖
![chrome-capture](https://user-images.githubusercontent.com/89329117/134791984-8e297ed4-d8d9-4c36-bd0b-e85051c046b6.gif)


## code
````c

int buttonState = 0;

void setup()
{
  pinMode(2, INPUT);
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  
  buttonState = digitalRead(2);
  if (buttonState == HIGH) {
  
    digitalWrite(9, HIGH);
    digitalWrite(5, LOW);
    
  } else {
    
    digitalWrite(9, LOW);
    digitalWrite(5, HIGH);
  }
  delay(10); 
}
````
