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

#define PIN_TASTER 3
#define PIN_LED 9

void setup() {
  Serial.begin(115200);
  pinMode(PIN_TASTER, INPUT_PULLUP);
  pinMode(PIN_LED, OUTPUT);
}

void loop() {
  bool zustandTaster = digitalRead(PIN_TASTER);
  digitalWrite(PIN_LED, zustandTaster);
  Serial.print("Zustand Taster: ");
  Serial.println(zustandTaster);
}