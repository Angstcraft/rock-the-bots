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

#define PIN_LED1 2
#define PIN_LED2 3

void setup() {
  pinMode(PIN_LED1, OUTPUT);
  pinMode(PIN_LED2, OUTPUT);
}

void loop() {
  digitalWrite(PIN_LED1, HIGH); // LED1 an
  delay(500);                   // 500ms
  digitalWrite(PIN_LED1, LOW);  // LED1 aus
  delay(300);                   // 300ms
  
  digitalWrite(PIN_LED2, HIGH); // LED2 an
  delay(700);                   // 700ms
  digitalWrite(PIN_LED2, LOW);  // LED2 aus
  delay(400);                   // 400ms
}