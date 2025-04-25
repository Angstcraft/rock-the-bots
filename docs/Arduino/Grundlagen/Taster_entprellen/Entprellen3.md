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
#define LED1 2
#define LED2 3
#define LED3 4
#define LED4 5

int ledIndex = 0;
const int gesamtLEDs = 4;

bool entprellen = false;
bool zustandTaster = HIGH;
bool zustandTasterAlt = HIGH;

unsigned long entprellZeit = 30;
unsigned long startEntprellen;

void setup() {
  pinMode(BUTTON, INPUT_PULLUP);
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  pinMode(LED3, OUTPUT);
  pinMode(LED4, OUTPUT);
  digitalWrite(LED1, HIGH);
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
        digitalWrite(ledIndex + 2, LOW); 
        ledIndex = (ledIndex + 1) % gesamtLEDs;
        digitalWrite(ledIndex + 2, HIGH); 
      entprellen = false;
    }
  }

  zustandTasterAlt = zustandTaster;
}