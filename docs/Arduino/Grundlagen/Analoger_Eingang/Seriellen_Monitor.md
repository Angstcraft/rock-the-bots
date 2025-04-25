# Title: [Seriellen_Monitor]

## General Tips
- [Tip 1]
- [Tip 2]
- [Tip 3]

## Task List
### Click below to view tasks:
<details>
  <summary>Click here to see tasks</summary>
  - [Task 1: Enter Task Description]
  
</details>

## Solutions

### Task 1: [Task Title]
```Arduino
 [#define pinPoti A0
#define maxBars 25

void setup() {
  Serial.begin(9600);
  pinMode(pinPoti, INPUT);
}

void loop() {
  int messWert = analogRead(pinPoti);
  int percent = map(messWert, 0, 1023, 0, 100);
  int numBars = map(messWert, 0, 1023, 0, maxBars);

  Serial.print(">");
  for (int i = 0; i < numBars; i++) {
    Serial.print(">");
  }
  for (int i = numBars; i < maxBars; i++) {
    Serial.print(".");
  }
  Serial.print(" [");
  Serial.print(percent);
  Serial.print("%]");
  Serial.println();

  delay(500);
}]

