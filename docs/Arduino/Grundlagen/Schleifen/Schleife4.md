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

int dTime = 200; bi

void setup() {
    for (int i = 2; i <= 6; i++) {
        pinMode(i, OUTPUT);
    }
}

void loop() {
        //ON
    for (int i = 2; i <= 6; i++) {
        digitalWrite(i, HIGH);
    }
    delay(dTime);
    
   //OFF
    for (int i = 2; i <= 6; i++) {
        digitalWrite(i, LOW);
    }
    delay(dTime);
}