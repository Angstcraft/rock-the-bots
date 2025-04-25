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

#define TASTER 3

unsigned long startZeit;
unsigned long druckZeit;

void setup() {
  pinMode(TASTER, INPUT);
  Serial.begin(9600);
}

void loop() {
  if (digitalRead(TASTER) == HIGH) {
    startZeit = millis();
    while (digitalRead(TASTER) == HIGH);
    druckZeit = millis() - startZeit;
    Serial.print("Zeit, die der Taster gedrückt war: ");
    Serial.print(druckZeit / 1000.0);
    Serial.println(" Sekunden");
  }
}