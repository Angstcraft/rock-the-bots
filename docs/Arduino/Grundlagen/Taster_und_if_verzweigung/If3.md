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

#define PIN_LED 3
#define PIN_TASTER 8

void setup() {
  pinMode(PIN_LED, OUTPUT);
  pinMode(PIN_TASTER, INPUT_PULLUP);
}

void loop() {
  int zustandTaster = digitalRead(PIN_TASTER);
  
  if (zustandTaster == HIGH) {
    digitalWrite(PIN_LED, HIGH);
  } else {
    digitalWrite(PIN_LED, LOW);
  }
}