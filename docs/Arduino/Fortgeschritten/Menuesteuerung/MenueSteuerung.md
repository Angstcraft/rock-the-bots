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

#include <Bounce2.h>

// Pin-Definitionen
const int pinUp = 2;          // Taster für das Ändern des Menüeintrags
const int pinSelect = 3;      // Taster für das Aktivieren des Menüeintrags
const int pinLed1 = 9;        // LED 1
const int pinLed2 = 10;       // LED 2
const int pinTaskRunning = 11; // LED zeigt, dass ein Task läuft

// Instanz für die Entprellung der Taster
Bounce debouncerUp = Bounce();
Bounce debouncerSelect = Bounce();

// Aufzählungsdatentyp für die Menüeinträge 
enum MenuStates { STATE0, STATE1, STATE2 };
MenuStates menuState = STATE0;

// Gibt an, ob ein Menüeintrag aktiviert ist.
bool taskIsRunning = false; 

void setup() {
  Serial.begin(9600);

  // LED-Pins als Ausgänge definieren
  pinMode(pinLed1, OUTPUT);
  pinMode(pinLed2, OUTPUT);
  pinMode(pinTaskRunning, OUTPUT);

  // Taster-Pins als Eingänge und mit Entprellung konfigurieren
  pinMode(pinUp, INPUT);
  debouncerUp.attach(pinUp);
  debouncerUp.interval(5);
  
  pinMode(pinSelect, INPUT);
  debouncerSelect.attach(pinSelect);
  debouncerSelect.interval(5);
}

void loop() {
  // Aktualisieren der Tasterzustände  
  debouncerSelect.update(); 
  debouncerUp.update();     

  if (taskIsRunning) {
    doTasks();
  }
  else {
    if (debouncerUp.fell()) { // Wenn Taster gedrückt
      doMenu();
    }
    if (debouncerSelect.fell()) { // Wenn Taster gedrückt
      taskIsRunning = true;
    }
  }
}

void doMenu() {
  switch (menuState) {
    case STATE0:
      menuState = STATE1;
      setLeds(0, 1);
      Serial.print("\n [Menue: STATE1] ");
      break;
    case STATE1:
      menuState = STATE2;
      setLeds(1, 0);
      Serial.print("\n [Menue: STATE2] ");
      break;
    case STATE2:
      menuState = STATE0;
      setLeds(0, 0);
      Serial.print("\n [Menue: STATE0] ");
      break;
  }
}

void setLeds(bool pLed1, bool pLed2) {
  digitalWrite(pinLed1, pLed1);
  digitalWrite(pinLed2, pLed2);
}

void doTasks() {
  switch (menuState) {
    case STATE0:
      taskIsRunning = !doEvent0();
      break;
    case STATE1:
      taskIsRunning = !doEvent1();
      break;
    case STATE2:
      taskIsRunning = !doEvent2();
      break;
  }
}

bool doEvent0() {
  digitalWrite(pinTaskRunning, HIGH);
  Serial.print("Event 0 is blocking for 1 sec . ");
  delay(1000);
  Serial.print("finished");
  digitalWrite(pinTaskRunning, LOW);
  return true;
}

bool doEvent1() {
  digitalWrite(pinTaskRunning, HIGH);
  Serial.print("Event 1 is blocking for 5 sec ..... ");
  delay(5000);
  Serial.print("finished");
  digitalWrite(pinTaskRunning, LOW);
  return true;
}

bool doEvent2() {
  digitalWrite(pinTaskRunning, HIGH);
  Serial.print("\n\t\tEvent 2 is running (Press Button) ");
  if (debouncerSelect.fell()) {
    Serial.print(" ... finished");
    digitalWrite(pinTaskRunning, LOW);
    return true;
  }
  else {
    return false;
  }
}