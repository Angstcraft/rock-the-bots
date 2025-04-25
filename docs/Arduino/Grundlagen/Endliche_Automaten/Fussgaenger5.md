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
#define FA_ROT 6
#define FA_GRUEN 5
#define PA_ROT 4
#define PA_GRUEN 3
#define BUTTON_PIN 2

enum Ampelzustand {FA_ROT, FA_GRUEN, PA_ROT, PA_GRUEN};
Ampelzustand zustand = PA_ROT;
unsigned long letzteZeit = 0;

void setup() {
  pinMode(FA_ROT, OUTPUT);
  pinMode(FA_GRUEN, OUTPUT);
  pinMode(PA_ROT, OUTPUT);
  pinMode(PA_GRUEN, OUTPUT);
  pinMode(BUTTON_PIN, INPUT_PULLUP);
}

void loop() {
  unsigned long intervall;

  switch (zustand) {
    case PA_ROT:
      digitalWrite(PA_ROT, HIGH);
      digitalWrite(FA_ROT, HIGH);
      while (digitalRead(BUTTON_PIN) == HIGH) {}
      zustand = FA_GRUEN;
      letzteZeit = millis();
      break;

    case FA_GRUEN:
      digitalWrite(FA_GRUEN, HIGH);
      intervall = 5000;
      if (millis() - letzteZeit >= intervall) {
        zustand = FA_ROT;
        digitalWrite(FA_GRUEN, LOW);
        letzteZeit = millis();
      }
      break;

    case FA_ROT:
      digitalWrite(FA_ROT, HIGH);
      intervall = 1000;
      if (millis() - letzteZeit >= intervall) {
        zustand = PA_GRUEN;
        digitalWrite(FA_ROT, LOW);
        letzteZeit = millis();
      }
      break;

    case PA_GRUEN:
      digitalWrite(PA_GRUEN, HIGH);
      intervall = 5000;
      if (millis() - letzteZeit >= intervall) {
        zustand = PA_ROT;
        digitalWrite(PA_GRUEN, LOW);
        letzteZeit = millis();
      }
      break;
  }
}
