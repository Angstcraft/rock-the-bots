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

#define BUTTON1 12
#define BUTTON2 13
#define LED1 2
#define LED2 3

bool entprellen1 = false;
bool entprellen2 = false;
bool zustandTaster1 = HIGH;
bool zustandTaster2 = HIGH;
bool zustandTasterAlt1 = HIGH;
bool zustandTasterAlt2 = HIGH;
bool zustandLed1 = LOW;
bool zustandLed2 = LOW;

unsigned long entprellZeit = 30;
unsigned long startEntprellen1;
unsigned long startEntprellen2;

void setup() {
  pinMode(BUTTON1, INPUT_PULLUP);
  pinMode(BUTTON2, INPUT_PULLUP);
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
}

void loop() {
  zustandTaster1 = digitalRead(BUTTON1);
  zustandTaster2 = digitalRead(BUTTON2);

  if ((zustandTaster1 == 0) && (zustandTasterAlt1 == 1)) {
    startEntprellen1 = millis();
    entprellen1 = true;
  }
  
  if (entprellen1) {
    if (millis() - startEntprellen1 > entprellZeit) {
      if (digitalRead(BUTTON1) == 0) {
        zustandLed1 = !zustandLed1;
        digitalWrite(LED1, zustandLed1);
      }
      entprellen1 = false;
    }
  }

  if ((zustandTaster2 == 0) && (zustandTasterAlt2 == 1)) {
    startEntprellen2 = millis();
    entprellen2 = true;
  }

  if (entprellen2) {
    if (millis() - startEntprellen2 > entprellZeit) {
      if (digitalRead(BUTTON2) == 0) {
        zustandLed2 = !zustandLed2;
        digitalWrite(LED2, zustandLed2);
      }
      entprellen2 = false;
    }
  }

  zustandTasterAlt1 = zustandTaster1;
  zustandTasterAlt2 = zustandTaster2;
}