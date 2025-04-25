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
int led1 = 2; 
int led2 = 3; 

void setup() {
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
}

void loop() {
  // Erste LED 3x blinken lassen
  for (int i = 0; i < 3; i++) {
    digitalWrite(led1, HIGH);
    delay(500);
    digitalWrite(led1, LOW);
    delay(500);
  }

  // Zweite LED 5x blinken lassen
  for (int i = 0; i < 5; i++) {
    digitalWrite(led2, HIGH);
    delay(500);
    digitalWrite(led2, LOW);
    delay(500);
  }
}
