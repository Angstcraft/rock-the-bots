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

#define PIN_TASTER1 A1  
#define PIN_TASTER2 A2  
const int IN1 = 5;     
const int IN2 = 6;     
const int LED_LINKS = 9; 
const int LED_RECHTS = 10; 

void setup() {
  Serial.begin(115200);
  
  pinMode(IN1, OUTPUT); 
  pinMode(IN2, OUTPUT);
  pinMode(PIN_TASTER1, INPUT_PULLUP); 
  pinMode(PIN_TASTER2, INPUT_PULLUP); 
  pinMode(LED_LINKS, OUTPUT); 
  pinMode(LED_RECHTS, OUTPUT); 
}

void loop() {
  int statusTaster1 = digitalRead(PIN_TASTER1);
  int statusTaster2 = digitalRead(PIN_TASTER2);

  if (statusTaster1 == LOW && statusTaster2 == LOW) { 
    stoppeMotorBremse();
  } 
  else if (statusTaster1 == LOW) { 
    dreheMotorRechts();
  } 
  else if (statusTaster2 == LOW) { 
    dreheMotorLinks();
  } 
  else { 
    stoppeMotorFreilauf();
  }
}

void dreheMotorLinks() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, HIGH);
  digitalWrite(LED_LINKS, HIGH); 
  digitalWrite(LED_RECHTS, LOW); 
}

void dreheMotorRechts() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
  digitalWrite(LED_LINKS, LOW); 
  digitalWrite(LED_RECHTS, HIGH); 
}

void stoppeMotorBremse() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, HIGH);
  digitalWrite(LED_LINKS, LOW); 
  digitalWrite(LED_RECHTS, LOW);
}

void stoppeMotorFreilauf() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);
  digitalWrite(LED_LINKS, LOW); 
  digitalWrite(LED_RECHTS, LOW);
}