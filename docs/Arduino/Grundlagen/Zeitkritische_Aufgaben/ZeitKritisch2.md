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

unsigned long zeitLetztesUmschalten = 0;
int zustandLED = LOW;

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(TASTER, INPUT);
}

void loop() {
  unsigned long aktuelleZeit = millis();
  int buttonState = digitalRead(TASTER);

  if (buttonState == HIGH) {
    if (aktuelleZeit - zeitLetztesUmschalten >= 250) {
      zustandLED = (zustandLED == LOW) ? HIGH : LOW;
      digitalWrite(LED, zustandLED);
      zeitLetztesUmschalten = aktuelleZeit;
    }
  } else {
    digitalWrite(LED, LOW);
    zustandLED = LOW;
  }
}