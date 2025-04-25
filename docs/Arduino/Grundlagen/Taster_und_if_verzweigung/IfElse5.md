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

void setup() {
    Serial.begin(115200);
  }
  
  void loop() {
    for (int i = 0; i <= 100; i++) {
      if (i % 3 == 0 && i % 5 == 0) {
        Serial.println("FizzBuzz");
      } else if (i % 3 == 0) {
        Serial.println("Fizz");
      } else if (i % 5 == 0) {
        Serial.println("Buzz");
      } else {
        Serial.println(i);
      }
    }
    while (true); // Stoppt die Schleife Cool oder? :)
  }