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
#define LED_1 6
#define LED_2 5
#define BUTTON_1 2
#define BUTTON_2 3

void setup() {
  pinMode(LED_1, OUTPUT);
  pinMode(LED_2, OUTPUT);
  pinMode(BUTTON_1, INPUT_PULLUP);
  pinMode(BUTTON_2, INPUT_PULLUP);
  Serial.begin(115200);

  Serial.println("-------------------------------");
  Serial.println("Reaktionstester bereit!");
}

void loop() {
  digitalWrite(LED_1, HIGH);
  while (digitalRead(BUTTON_1) == HIGH) {}

  Serial.println("Warten auf das rote Licht ...");
  delay(random(2000, 5000));
  digitalWrite(LED_2, HIGH);
  unsigned long startTime = millis();
  while (digitalRead(BUTTON_2) == HIGH) {
    digitalWrite(LED_1, !digitalRead(LED_1));
    delay(100);
  }
  digitalWrite(LED_1, LOW);
  unsigned long reactionTime = millis() - startTime;
  Serial.print("Reaktionszeit: ");
  Serial.print(reactionTime / 1000.0);
  Serial.println(" Sekunden");
  delay(2000);
}
