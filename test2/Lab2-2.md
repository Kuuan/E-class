# 實作2-2, RGB LED燈全彩模組, 分別讓LED輪流表現正紅、正綠、正藍，三個顏色，時間間隔1秒鐘。並且觀查LED顏色和波形或是電壓有什麼關連性?

## 電路圖

![image](https://user-images.githubusercontent.com/89329117/132114864-fd8fa047-ee03-4233-9cd6-4eecfabb1380.png)

## CODE

````c
const int R=10;
const int G=8;
const int B=9;

void setup()
{
  pinMode(10, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(8, OUTPUT);
}

void loop()
{

  analogWrite(R, 255);
  analogWrite(G,0);
  analogWrite(B,0);
  delay(1000); 
  
  analogWrite(R,0);
  analogWrite(G,255);
  analogWrite(B,0);
  delay(1000); 
  
  analogWrite(R,0);
  analogWrite(G,0);
  analogWrite(B,255);
  delay(1000); 
}
````
