# 如下圖的Demo, 用七段顯示器, 顯示 . →1→ ... → 9 → 0 → 全滅, 狀態改變的間隔時間為0.5秒

# 電路圖
![chrome-capture (2)](https://user-images.githubusercontent.com/89329117/137610059-e90cf628-c38c-4b17-9a36-6f0bc5322073.gif)

#CODE
````c
void setup()
{
for(int x = 1; x < 9; x++) {
pinMode(x,OUTPUT);
}
}

void seg71(int a, int b, int c, int d, int e, int f, int g, int h)
{
digitalWrite(1, a);
digitalWrite(2, b);
digitalWrite(3, c);
digitalWrite(4, d);
digitalWrite(5, e);
digitalWrite(6, f);
digitalWrite(7, g);
digitalWrite(8, h);
delay(500);
}

void loop()
{
//    a, b, c, d, e, f, g, h
seg71(0, 0, 0, 0, 0, 0, 0, 0); // OFF
seg71(1, 1, 1, 1, 1, 1, 1, 1); // 8
seg71(0, 0, 0, 0, 0, 0, 0, 1); // .
seg71(1, 1, 1, 1, 1, 1, 0, 0); // 0
seg71(0, 1, 1, 0, 0, 0, 0, 0); // 1
seg71(1, 1, 0, 1, 1, 0, 1, 0); // 2
seg71(1, 1, 1, 1, 0, 0, 1, 0); // 3
seg71(0, 1, 1, 0, 0, 1, 1, 0); // 4
seg71(1, 0, 1, 1, 0, 1, 1, 0); // 5
seg71(1, 0, 1, 1, 1, 1, 1, 0); // 6
seg71(1, 1, 1, 0, 0, 0, 0, 0); // 7
seg71(1, 1, 1, 1, 1, 1, 1, 0); // 8  
seg71(1, 1, 1, 1, 0, 1, 1, 0); // 9
}
````
