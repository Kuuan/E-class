# 實作2-3, 讓你的RGB LED燈全彩模組也可會"呼吸", LED顏色變化是否有像"呼吸的效果"和示波器的波形有什麼關連性? (互動3)

## 電路圖
![image](https://user-images.githubusercontent.com/89329117/132970598-9380f62a-3077-40b2-93db-00fef4e10828.png)

### CODE

````c
int R = 10;
int G = 7;
int B = 8;

int R2 = 5;
int G2 = 2;
int B2 = 3;

void setup()
{
  pinMode(11, OUTPUT);
  
  pinMode(R, OUTPUT);
  pinMode(G, OUTPUT);
  pinMode(B, OUTPUT);  
  
  pinMode(R2, OUTPUT);
  pinMode(G2, OUTPUT);
  pinMode(B2, OUTPUT);   
}

void loop()
{
 
  digitalWrite(11, 1); 
  
  delay(1000); 
  
  digitalWrite(R2, 1);
  digitalWrite(G2, 0);
  digitalWrite(B2, 0);
  delay(1000);
  digitalWrite(R2, 0);
  digitalWrite(G2, 1);
  digitalWrite(B2, 0);  
  delay(1000);
  digitalWrite(R2, 0);
  digitalWrite(G2, 0);
  digitalWrite(B2, 1);  
  delay(1000);

  digitalWrite(11, 0); 
  digitalWrite(R2, 0); 
  digitalWrite(G2, 0); 
  digitalWrite(B2, 0);
  delay(1000);
  
 
  for (int i = 0; i<= 255; i++)
  {
  	analogWrite(R, i);
		analogWrite(G, 0);
		analogWrite(B, 0);
    delay(10);
  }

  for (int i = 255; i>= 0; i--)
  {
  	analogWrite(R, i);
		analogWrite(G, 0);
		analogWrite(B, 0);
    delay(10); 
  }  
  delay(1000);
}

````
