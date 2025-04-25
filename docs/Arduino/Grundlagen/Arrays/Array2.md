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
#define NUMLED 5
int pinLeds[NUMLED] = {3, 5, 6, 9, 10};
#define BUTTON_LEFT 12
#define BUTTON_RIGHT 13

int currentLed = 0;
bool entprellenLeft = false;
bool entprellenRight = false;
unsigned long lastPressLeft;
unsigned long lastPressRight;
unsigned long debounceDelay = 30;

void setup() {
  for (int i = 0; i < NUMLED; i++) {
    pinMode(pinLeds[i], OUTPUT);
    digitalWrite(pinLeds[i], LOW);
  }
  pinMode(BUTTON_LEFT, INPUT_PULLUP);
  pinMode(BUTTON_RIGHT, INPUT_PULLUP);
  digitalWrite(pinLeds[currentLed], HIGH);
}

void loop() {
  if (digitalRead(BUTTON_LEFT) == LOW && !entprellenLeft) {
    lastPressLeft = millis();
    entprellenLeft = true;
  }
  
  if (entprellenLeft && (millis() - lastPressLeft > debounceDelay)) {
    currentLed = (currentLed - 1 + NUMLED) % NUMLED;
    manageLEDs();
    entprellenLeft = false;
  }

  if (digitalRead(BUTTON_RIGHT) == LOW && !entprellenRight) {
    lastPressRight = millis();
    entprellenRight = true;
  }
  
  if (entprellenRight && (millis() - lastPressRight > debounceDelay)) {
    currentLed = (currentLed + 1) % NUMLED;
    manageLEDs();
    entprellenRight = false;
  }
}

void manageLEDs() {
  for (int i = 0; i < NUMLED; i++) {
    digitalWrite(pinLeds[i], LOW);
  }
  digitalWrite(pinLeds[currentLed], HIGH);
}
