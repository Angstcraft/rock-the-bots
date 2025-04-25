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

#define PIN_LED1 3
#define PIN_LED2 4
#define PIN_TASTER1 8
#define PIN_TASTER2 9

void setup() {
  pinMode(PIN_LED1, OUTPUT);
  pinMode(PIN_LED2, OUTPUT);
  pinMode(PIN_TASTER1, INPUT_PULLUP);
  pinMode(PIN_TASTER2, INPUT_PULLUP);
}

void loop() {
  int zustandTaster1 = digitalRead(PIN_TASTER1);
  int zustandTaster2 = digitalRead(PIN_TASTER2);

  if (zustandTaster1 == LOW) {
    digitalWrite(PIN_LED1, HIGH);
  } else if (zustandTaster2 == LOW) {
    digitalWrite(PIN_LED2, HIGH);
  } else if (zustandTaster1 == LOW && zustandTaster2 == LOW) {
    digitalWrite(PIN_LED1, HIGH);
    digitalWrite(PIN_LED2, HIGH);
  } else {
    digitalWrite(PIN_LED1, LOW);
    digitalWrite(PIN_LED2, LOW);
  }
}