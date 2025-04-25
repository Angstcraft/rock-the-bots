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
    int i, j;
  
    for (i = 0; i < 10; i++) {
      Serial.print("Zeile: "); 
      Serial.print(i); 
      for (j = 0; j <= i; j++) {
        Serial.print("*");
      }
      Serial.println();
    }
  }
  
  void loop() {
  }