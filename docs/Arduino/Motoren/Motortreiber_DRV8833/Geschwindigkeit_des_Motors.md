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

#define PIN_TASTER_HOCH A1  
#define PIN_TASTER_RUNTER A2  
const int IN1 = 5;     
const int IN2 = 6;     

int motorSpeed = 0;    

void setup() {
  Serial.begin(115200);
  pinMode(IN1, OUTPUT); 
  pinMode(IN2, OUTPUT);
  pinMode(PIN_TASTER_HOCH, INPUT_PULLUP); 
  pinMode(PIN_TASTER_RUNTER, INPUT_PULLUP); 
}

void loop() {
  int statusTasterHoch = digitalRead(PIN_TASTER_HOCH);
  int statusTasterRunter = digitalRead(PIN_TASTER_RUNTER);
  
  if (statusTasterHoch == LOW) { 
    motorSpeed += 15; 
    if (motorSpeed > 255) motorSpeed = 255; 
    analogWrite(IN1, motorSpeed); 
    digitalWrite(IN2, LOW);
    Serial.print("Geschwindigkeit erhöht: ");
    Serial.println(motorSpeed);
  } 
  else if (statusTasterRunter == LOW) { 
    motorSpeed -= 15; 
    if (motorSpeed < 0) motorSpeed = 0; 
    analogWrite(IN1, motorSpeed); 
    digitalWrite(IN2, LOW);
    Serial.print("Geschwindigkeit verringert: ");
    Serial.println(motorSpeed);
  } 
  else if (statusTasterHoch == LOW && statusTasterRunter == LOW) { 
    stoppeMotorBremse();
  } 
  else { 
    digitalWrite(IN1, LOW);
    digitalWrite(IN2, LOW);
    Serial.println("Motor im Freilauf");
  }
}

void stoppeMotorBremse() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, HIGH);
  motorSpeed = 0; 
  Serial.println("Motor wird gebremst");
}