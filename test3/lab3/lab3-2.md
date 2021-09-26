# 超音波感測器 + LED (紅色LED:亮<70cm, 緑色LED: 亮>270cm, 藍色LED:亮, 介於70cm ~ 270cm之間) + RS232 Output

## 電路圖
![chrome-capture (3)](https://user-images.githubusercontent.com/89329117/134792900-afd24909-c75d-4245-b952-c68abe95ecc0.gif)

## CODE
````c
int inches = 0;
int GLED = 10;
int RLED = 13;
int BLED = 11;
int cm = 0;

void LED(int RH,int GH,int BH)
{
  digitalWrite(RLED, RH);
  digitalWrite(GLED, GH);
  digitalWrite(BLED, BH);
}

long readUltrasonicDistance(int triggerPin, int echoPin)
{
  pinMode(triggerPin, OUTPUT);  // Clear the trigger
  digitalWrite(triggerPin, LOW);
  delayMicroseconds(2);
  // Sets the trigger pin to HIGH state for 10 microseconds
  digitalWrite(triggerPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(triggerPin, LOW);
  pinMode(echoPin, INPUT);
  // Reads the echo pin, and returns the sound wave travel time in microseconds
  return pulseIn(echoPin, HIGH);
}


void setup()
{
  Serial.begin(9600);
  digitalWrite(RLED, OUTPUT);
  digitalWrite(GLED, OUTPUT);
  digitalWrite(BLED, OUTPUT);

}

void loop()
{
  // measure the ping time in cm
  cm = 0.01723 * readUltrasonicDistance(7, 7);

  // convert to inches by dividing by 2.54
  inches = (cm / 2.54);
  Serial.print(inches);
  Serial.print("in, ");
  Serial.print(cm);
  
  if(cm<70){
    LED(1,0,0);
  }
  else if(cm>270){
    LED(0,1,0);
  }
  else{
    LED(0,0,1);
  }
  
  Serial.println("cm");
  delay(100); // Wait for 100 millisecond(s)
}
````
