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
    Serial.begin(9600);
    float dutyCycle = 201.0 / 255.0 * 100.0;
    Serial.println("Tastverhältnis (%): " + String(dutyCycle));
  }
  
  void loop() {}