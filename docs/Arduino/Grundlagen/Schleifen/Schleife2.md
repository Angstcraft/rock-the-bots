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

int led = 2;  
int delayTime = 1000;  

void setup() {
  pinMode(led, OUTPUT);
}

void loop() {
  // LED blinken lassen
  digitalWrite(led, HIGH);
  delay(delayTime);
  digitalWrite(led, LOW);
  delay(delayTime);
  
  // Verzögerung schrittweise erhöhen oder verringern
  if (delayTime > 50) {
    delayTime -= 50;  // Schneller werden
  } else {
    delayTime = 1000;  // Reset auf langsamer Blinkrhythmus
  }
}