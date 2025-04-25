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

#define TASTER 3
#define LED 13

bool statusLED = LOW;
bool statusTaster = HIGH;
bool statusTasterLetzter = HIGH;
int zaehler = 0;

void setup() {
  pinMode(TASTER, INPUT_PULLUP);
  pinMode(LED, OUTPUT);
  Serial.begin(115200);
} 

void loop() {
  statusTaster = digitalRead(TASTER);
  
  if (statusTaster != statusTasterLetzter) {
    if (statusTaster == LOW) {
      statusLED = !statusLED;
      zaehler++;
      Serial.print("Umschaltung: "); 
      Serial.println(zaehler);
    }
  }

  statusTasterLetzter = statusTaster;
  digitalWrite(LED, statusLED);
}