# Title: [Funky]

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
  Serial.begin(115200);
  pinMode(PIN_LED, OUTPUT);
}

void loop() {
  gruessen();
  delay(1000);
  aufblinken();
  delay(1000);
}

void gruessen() {
  Serial.println("Hallo Welt, wie geht es?");
}

//2 Aufgabe ,)
void aufblinken() {
  digitalWrite(PIN_LED, HIGH); 
  delay(200);                  
  digitalWrite(PIN_LED, LOW);
}