# Title: [PotentioMeter]

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
  int numLeds = map(messWert, 0, 1023, 0, ledCount);

  for (int i = 0; i < ledCount; i++) {
    if (i < numLeds) {
      digitalWrite(ledPins[i], HIGH);
    } else {
      digitalWrite(ledPins[i], LOW);
    }
  }
  delay(100);
}]

