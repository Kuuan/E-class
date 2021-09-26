# 實作2-5: 按下按鍵, Green LED亮 & Red LED滅; 放開按鍵, Green LED滅 & Red LED亮.

## 電路圖
![chrome-capture (1)](https://user-images.githubusercontent.com/89329117/134792367-ec7da684-a05d-4b5e-91c8-383459997873.gif)


## code
````c

int buttonState = 0;

void setup()
{
  pinMode(2, INPUT);
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
