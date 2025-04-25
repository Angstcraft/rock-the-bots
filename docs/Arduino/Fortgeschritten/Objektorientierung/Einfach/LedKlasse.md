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

#include <Arduino.h>  // Importiere Arduino-Bibliothek

class Led {
    int pinLed;       // Pin-Nummer der LED
    bool stateLed;    // Zustand der LED

  public:
    Led(int pPin) {   // Konstruktor
      // Setze den Pin und initialisiere den Zustand
    }
    
    void toggle() {    // Methode zum Umschalten
      // Ändere den Zustand der LED
    }
};