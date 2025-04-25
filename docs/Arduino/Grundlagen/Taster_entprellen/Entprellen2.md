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
#define BUTTON 12
#define LED 3

bool entprellen = false;
bool zustandTaster = HIGH;
bool zustandTasterAlt = HIGH;
bool zustandLed = LOW;

unsigned long entprellZeit = 30;
unsigned long startEntprellen;

void setup() {
  Serial.begin(115200);
  pinMode(BUTTON, INPUT_PULLUP);
  pinMode(LED, OUTPUT);
}

void loop() {
  zustandTaster = digitalRead(BUTTON);

  if ((zustandTaster == 0) && (zustandTasterAlt == 1)) {
    startEntprellen = millis();
    entprellen = true;
  }

  if (entprellen) {
    if (millis() - startEntprellen > entprellZeit) {
      if (digitalRead(BUTTON) == 0) {
        zustandLed = !zustandLed; 
        digitalWrite(LED, zustandLed);
      }
      entprellen = false;
    }
  }

  zustandTasterAlt = zustandTaster;
} 
