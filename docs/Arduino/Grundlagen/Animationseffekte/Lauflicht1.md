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
 #define NUMLED 6
const int pinsLED[] = {3, 5, 6, 9, 10, 11};
int ledStates[NUMLED] = {0, 0, 0, 0, 0, 0};
unsigned long lastTime = 0;
unsigned long delayMillis = 100;
int activeLed = 0;

void setup() {
  for (int i = 0; i < NUMLED; i++) {
    pinMode(pinsLED[i], OUTPUT);
  }
}

void showLeds(int pLedStates[]) {
  for (int i = 0; i < NUMLED; i++) {
    digitalWrite(pinsLED[i], pLedStates[i]);
  }
}

void clear() {
  for (int i = 0; i < NUMLED; i++) {
    ledStates[i] = 0;
  }
}

void loop() {
  if ((millis() - lastTime) > delayMillis) {
    clear();
    ledStates[activeLed] = 1;
    showLeds(ledStates);
    activeLed = (activeLed + 1) % NUMLED;
    lastTime = millis();
  }
}

