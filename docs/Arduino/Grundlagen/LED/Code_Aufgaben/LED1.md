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

#define PIN_LED 2

void setup() {
  pinMode(PIN_LED, OUTPUT);
}

void loop() {
  digitalWrite(PIN_LED, LOW);  // LED aus (90% der Zeit)
  delay(1800);                 // 1800ms = 1.8s
  digitalWrite(PIN_LED, HIGH); // LED an
  delay(200);                  // 200ms = 0.2s
}