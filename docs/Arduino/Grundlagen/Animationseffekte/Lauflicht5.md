# Title: [Your Title Here]

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
 [Write your code example here]
 #define NUMLED 6
 const int pinsLED[] = {3, 5, 6, 9, 10, 11};
 int ledStates[NUMLED] = {0, 0, 0, 0, 0, 0};
 unsigned long lastTime = 0;
 int currentLed = 0;
 int fadeValue = 255;
 unsigned long fadeDelay;

 void setup() {
  for (int i = 0; i < NUMLED; i++) {
    pinMode(pinsLED[i], OUTPUT);
  }
 }

 void showLeds() {
  for (int i = 0; i < NUMLED; i++) {
    analogWrite(pinsLED[i], ledStates[i]);
  }
 }

 void clear() {
  for (int i = 0; i < NUMLED; i++) {
    ledStates[i] = 0;
  }
 }

 void loop() {
  fadeDelay = map(analogRead(A0), 0, 1023, 10, 100);
  
  if (digitalRead(2) == HIGH) {
    fadeValue -= 5;
    if (fadeValue < 0) {
      fadeValue = 0;
      currentLed = (currentLed + 1) % NUMLED;
      fadeValue = 255;
    }
  }
  
  ledStates[currentLed] = fadeValue;
  showLeds();
  
  delay(fadeDelay);
 }