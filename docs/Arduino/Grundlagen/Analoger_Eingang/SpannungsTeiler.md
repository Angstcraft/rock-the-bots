# Title: [spannungsTeiler]

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
 [#define pinPoti A0
#define totalVoltage 5.0
#define R1 220.0
#define R2 500.0

void setup() {
  Serial.begin(9600);
  pinMode(pinPoti, INPUT);
}

void loop() {
  int messWert = analogRead(pinPoti);
  float measuredVoltage = (messWert / 1023.0) * totalVoltage;
  
  float voltageR1 = (R2 / (R1 + R2)) * totalVoltage;
  float voltageR2 = (R1 / (R1 + R2)) * totalVoltage;

  Serial.print("Messwert: ");
  Serial.print(messWert);
  Serial.print(" -> Spannung: ");
  Serial.print(measuredVoltage);
  Serial.print(" V | R1: ");
  Serial.print(voltageR1);
  Serial.print(" V | R2: ");
  Serial.println(voltageR2);

  delay(1000);
}]

