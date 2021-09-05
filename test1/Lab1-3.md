# 1-3 在TinkerCAD開一個新的Circuit, 分別使甪R, G, B三種顏色的LED, 讓LED ON, OFF的順序為R >> G >> B >> G >> R .... 無限循環.

## 電路圖

![image](https://user-images.githubusercontent.com/89329117/132115030-4be949e9-c32c-47ac-8326-e4fc0138ab3d.png)


## CODE
````c
void setup()
{
  pinMode(13, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(6, OUTPUT);
}

void loop()
{
  digitalWrite(13, HIGH);
  delay(1000);
  digitalWrite(13, LOW);
  delay(1000);
  digitalWrite(10, HIGH);
  delay(1000);
  digitalWrite(10, LOW);
  delay(1000);
  digitalWrite(6, HIGH);
  delay(1000); 
  digitalWrite(6, LOW);
  delay(1000);
}
````
