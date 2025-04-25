# Title: [LED_Dimmer]

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
#define ledCount 7
int ledPins[ledCount] = {2, 3, 4, 5, 6, 7, 8};

void setup() {
  for (int i = 0; i < ledCount; i++) {
    pinMode(ledPins[i], OUTPUT);
  }
  pinMode(pinPoti, INPUT);
}

void loop() {
  int messWert = analogRead(pinPoti);
  int pwmValue = map(messWert, 0, 1023, 0, 255);
  
  for (int i = 0; i < ledCount; i++) {
    if (i < (messWert / (1024 / ledCount))) {
      analogWrite(ledPins[i], pwmValue);
    } else {
      analogWrite(ledPins[i], 0);
    }
  }
  delay(100);
}]

