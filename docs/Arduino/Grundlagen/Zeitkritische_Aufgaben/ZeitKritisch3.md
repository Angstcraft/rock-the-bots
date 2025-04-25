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

#define LED 2
#define TASTER 3

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(TASTER, INPUT);
  unsigned long blinkZeit = 500;
  unsigned long zeitLetztesBlinken = 0;

  while (digitalRead(TASTER) == LOW) {
    unsigned long aktuelleZeit = millis();

    if (aktuelleZeit - zeitLetztesBlinken >= blinkZeit) {
      digitalWrite(LED, !digitalRead(LED));
      zeitLetztesBlinken = aktuelleZeit;
    }
  }
  
  digitalWrite(LED, LOW);
  Serial.begin(9600);
  Serial.println("Programm startet ...");
}

void loop() {
}