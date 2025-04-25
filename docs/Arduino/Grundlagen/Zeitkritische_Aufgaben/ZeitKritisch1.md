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

#define LED1 2
#define LED2 3

unsigned long zeitLetztesUmschalten1 = 0;
unsigned long zeitLetztesUmschalten2 = 0;
unsigned long blinkZeit1 = 500;
unsigned long blinkZeit2 = 1000;
int zustandLED1 = LOW;
int zustandLED2 = LOW;

void setup() {
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
}

void loop() {
  unsigned long aktuelleZeit = millis();
  
  if (aktuelleZeit - zeitLetztesUmschalten1 >= blinkZeit1) {
    zustandLED1 = (zustandLED1 == LOW) ? HIGH : LOW;
    digitalWrite(LED1, zustandLED1);
    zeitLetztesUmschalten1 = aktuelleZeit;
  }

  if (aktuelleZeit - zeitLetztesUmschalten2 >= blinkZeit2) {
    zustandLED2 = (zustandLED2 == LOW) ? HIGH : LOW;
    digitalWrite(LED2, zustandLED2);
    zeitLetztesUmschalten2 = aktuelleZeit;
  }
}