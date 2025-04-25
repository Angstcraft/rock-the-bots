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

#define LED1 5
#define LED2 6

void setup() {
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
}

void loop() {
  blinkenLED(LED1, 1000);
  blinkenLED(LED2, 500);
  
  codierenBuchstabe('S');
  codierenBuchstabe('O');
  codierenBuchstabe('S');
  zeigeWortabstand();
}

void blinkenLED(int pPin, int pPeriodendauer) {
  digitalWrite(pPin, HIGH);
  delay(pPeriodendauer / 2);
  digitalWrite(pPin, LOW);
  delay(pPeriodendauer / 2);
}

void schalten(int pPin, bool pZustand) {
  digitalWrite(pPin, pZustand ? HIGH : LOW);
}

void codierenBuchstabe(char pBuchstabe) {
  if (pBuchstabe == 'S') {
    schalten(LED1, HIGH);
    delay(200);
    schalten(LED1, LOW);
    delay(200);
    
    schalten(LED1, HIGH);
    delay(200);
    schalten(LED1, LOW);
    delay(200);
    
    schalten(LED1, HIGH);
    delay(200);
    schalten(LED1, LOW);
    delay(600);
  }
  else if (pBuchstabe == 'O') {
    schalten(LED1, HIGH);
    delay(600);
    schalten(LED1, LOW);
    delay(200);
    
    schalten(LED1, HIGH);
    delay(600);
    schalten(LED1, LOW);
    delay(200);
    
    schalten(LED1, HIGH);
    delay(600);
    schalten(LED1, LOW);
    delay(600);
  }
}

void zeigeWortabstand() {
  delay(1400);
}