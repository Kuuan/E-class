# 實作2-4 analogRead(), 1024解析度 (i.e.,10-bit): 可變電阻 + 序列監視器與輸出; 當你改變可變電阻的阻值(e.g., 10K-ohm)時，序列監視器輸出的數值有什麼改變?

## 電路圖
![image](https://user-images.githubusercontent.com/89329117/132971529-99e54c5a-5054-47ae-bda5-ba887866cf43.png)

## Code
````c 

int sensorValue = 0;

void setup()
{
  pinMode(A0, INPUT);
  Serial.begin(9600);
}

void loop()
{
  sensorValue = analogRead(A0);
  Serial.println(sensorValue);
  delay(10); 
}

````
