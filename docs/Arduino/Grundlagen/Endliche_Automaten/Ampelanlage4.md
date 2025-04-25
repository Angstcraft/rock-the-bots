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

#define RED_PIN 6
#define YELLOW_PIN 5
#define GREEN_PIN 4
#define BUTTON_PIN 2

enum Ampelzustand {ROT, ROT_GELB, GRUEN, GELB};
Ampelzustand zustand = ROT;
unsigned long letzteZeit = 0;

void setup() {
  pinMode(RED_PIN, OUTPUT);
  pinMode(YELLOW_PIN, OUTPUT);
  pinMode(GREEN_PIN, OUTPUT);
  pinMode(BUTTON_PIN, INPUT_PULLUP);
}

void loop() {
  unsigned long intervall;

  switch (zustand) {
    case ROT:
      digitalWrite(RED_PIN, HIGH);
      intervall = 3000;
      if (millis() - letzteZeit >= intervall) {
        letzteZeit = millis();
        zustand = ROT_GELB;
      }
      break;

    case ROT_GELB:
      digitalWrite(YELLOW_PIN, HIGH);
      intervall = 500;
      if (millis() - letzteZeit >= intervall) {
        letzteZeit = millis();
        zustand = GRUEN;
        digitalWrite(YELLOW_PIN, LOW);
      }
      break;

    case GRUEN:
      digitalWrite(GREEN_PIN, HIGH);
      intervall = 3000;
      if (millis() - letzteZeit >= intervall) {
        letzteZeit = millis();
        zustand = GELB;
        digitalWrite(GREEN_PIN, LOW);
      }
      break;

    case GELB:
      digitalWrite(YELLOW_PIN, HIGH);
      intervall = 1000;
      if (millis() - letzteZeit >= intervall) {
        letzteZeit = millis();
        zustand = ROT;
        digitalWrite(YELLOW_PIN, LOW);
      }
      break;
  }
}