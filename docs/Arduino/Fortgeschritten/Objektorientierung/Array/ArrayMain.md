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
#define LED_COUNT 5 // Anzahl der LEDs

class Led {
    int pinLed;       // Pin für die LED
    bool stateLed;    // Zustand der LED

  public:
    Led(int pPin) {
      pinLed = pPin; 
      stateLed = false; // Initialisiere die LED als aus
      pinMode(pinLed, OUTPUT); // Pin als Ausgang setzen
    }
    
    void anschalten() { // LED einschalten
      stateLed = true; 
      digitalWrite(pinLed, HIGH);
    }
    
    void ausschalten() { // LED ausschalten
      stateLed = false; 
      digitalWrite(pinLed, LOW);
    }
    
    void toggle() { // Zustand umschalten
      if (stateLed) ausschalten();
      else anschalten();
    }
};

Led ledListe[LED_COUNT] = {Led(3), Led(4), Led(5), Led(6), Led(7)}; // Array aus 5 LEDs

void setup() {
  // Keine speziellen Initialisierungen erforderlich, da sie im Konstruktor der Led-Klasse erfolgen
}

void loop() {
  // Blinkmuster
  for (int i = 0; i < LED_COUNT; i++) {
    ledListe[i].anschalten(); // current LED einschalten
    delay(300); // warte 300 ms
    ledListe[i].ausschalten(); // current LED ausschalten
    delay(100); // kurze Pause vor der nächsten LED
  }
}
