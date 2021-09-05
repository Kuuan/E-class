# 1-2 在TinkerCAD開一個新的Circuit, 分別使甪R, G, B三種顏色的LED, ON (亮) 0.5秒, OFF(滅) 0.5秒

## 電路圖

![image](https://user-images.githubusercontent.com/89329117/132113782-e5201ad5-db14-4d3f-a93f-c072371764b5.png)

## CODE

````C
void setup()
{
  pinMode(13, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(6, OUTPUT);
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(13, HIGH);
  digitalWrite(10, HIGH);
  digitalWrite(6, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  // turn the LED off by making the voltage LOW
  digitalWrite(13, LOW);
  digitalWrite(10, LOW);
  digitalWrite(6, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
````
