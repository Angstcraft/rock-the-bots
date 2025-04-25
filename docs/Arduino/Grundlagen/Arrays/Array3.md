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
const int pinLeds[NUMLED] = {3, 5, 6, 9, 10, 11};
int zustandLeds[] = {0, 0, 0, 0, 0, 0};
int dir = 1;
int num = 0;

unsigned long lastTime = 0;
unsigned long delayMillis = 200;

void setup() {
  for (int i = 0; i < NUMLED; i++) {
    pinMode(pinLeds[i], OUTPUT);
  }
}

void loop() {
  if ((millis() - lastTime) > delayMillis) {
    for (int i = 0; i < NUMLED; i++) {
      if (i == num) {
        zustandLeds[i] = HIGH;
      } else {
        zustandLeds[i] = LOW;
      }
      digitalWrite(pinLeds[i], zustandLeds[i]);
    }

    if (num >= NUMLED-1) {
      dir = -1;
    } else if (num == 0) {
      dir = 1;
    }
    num += dir;

    lastTime = millis();
  }
}
