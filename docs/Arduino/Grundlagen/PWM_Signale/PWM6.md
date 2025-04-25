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

int ledPins[] = {3, 5, 6, 9, 10, 11};
int numLeds = 6;

void setup() {
  for (int i = 0; i < numLeds; i++) {
    pinMode(ledPins[i], OUTPUT);
  }
}

void loop() {
  for (int i = 0; i < numLeds; i++) {
    for (int brightness = 255; brightness >= 0; brightness -= 51) {
      analogWrite(ledPins[i], brightness);
      delay(50);
    }
  }
  
  for (int i = numLeds - 1; i >= 0; i--) {
    for (int brightness = 255; brightness >= 0; brightness -= 51) {
      analogWrite(ledPins[i], brightness);
      delay(50);
    }
  }
}