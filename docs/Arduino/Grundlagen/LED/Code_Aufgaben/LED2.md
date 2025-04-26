# LED2

## General Tips
- [Tip 1]
- [Tip 2]
- [Tip 3]

## Task List
### Click below to view tasks:
<details>
  <summary>Click here to see tasks</summary>
  - [Lassen Sie die LED das SOS Signal morsen (3x kurz, 3x lang, 3x kurz).]
  
</details>

## Solutions

### Task 1: SOS
```Arduino
 [Write your code example here]

#define PIN_LED 2

void setup() {
  pinMode(PIN_LED, OUTPUT);
}

void loop() {
  // SOS: "... --- ..."--- ..."
  //In der Telegraphie ist ein ... s und --- ein o
  //Es ist auch wichtig das in ein Rythmus uebertragen wird

  for (int i = 0; i < 3; i++) {
    digitalWrite(PIN_LED, HIGH); // kurz an
    delay(200);                  // 200ms
    digitalWrite(PIN_LED, LOW);  // aus
    delay(200);                  // 200ms
  }
  delay(600);                    // um den Rythmus zu bestimmen

  for (int i = 0; i < 3; i++) {
    digitalWrite(PIN_LED, HIGH); // lang an
    delay(600);                  // 600ms
    digitalWrite(PIN_LED, LOW);  // aus
    delay(200);                  // kurz aus
  }
  delay(600);                    // hier wieder um den Rythmus zu bestmmen
}