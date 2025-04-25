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

class Blinker {
    int onTime;  // An-Zeit in Millisekunden
    int offTime; // Aus-Zeit in Millisekunden
    int pinLed;  // Pin für die LED
    int stateLed; // Zustand der LED
    unsigned long lastTime; // Zeitstempel des letzten Umschaltens

  public:
    Blinker(int pin) {
      onTime = 1000; // Standardwerte
      offTime = 1000; // Standardwerte
      pinLed = pin;
      lastTime = 0; // Initialisiere die Zeit
      stateLed = LOW; // Zustand ist aus
      // Initialisierung des LED-Pins
    }

    void update() {
      // Zeit seit dem letzten Umschalten prüfen und die LED umschalten, 
      // wenn die Zeit abgelaufen ist
    }

    void setBlink(int pOn, int pOff) {
      onTime = pOn; // An-Zeit festlegen
      offTime = pOff; // Aus-Zeit festlegen
    }
};