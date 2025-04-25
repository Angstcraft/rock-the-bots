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
#define NUM_ELEMENTS 10
int zahlen[NUM_ELEMENTS] = {5, 12, 56, 2, 89, 45, 23, 56, 89, 12};

void setup() {
  Serial.begin(115200);
  delay(1000);

  int sum = 0;
  int max = zahlen[0];
  int min = zahlen[0];

  for(int i = 0; i < NUM_ELEMENTS; i++) {
    sum += zahlen[i];

    if(zahlen[i] > max) {
      max = zahlen[i];
    }

    if(zahlen[i] < min) {
      min = zahlen[i];
    }
  }

  float average = sum / (float)NUM_ELEMENTS;

  Serial.print("Mittelwert: ");
  Serial.println(average);
  Serial.print("Größter Wert: ");
  Serial.println(max);
  Serial.print("Kleinster Wert: ");
  Serial.println(min);

  int sortedZahlen[NUM_ELEMENTS];
  memcpy(sortedZahlen, zahlen, sizeof(zahlen));
  sortArray(sortedZahlen, NUM_ELEMENTS);

  float median;
  if (NUM_ELEMENTS % 2 == 0) {
    median = (sortedZahlen[NUM_ELEMENTS / 2 - 1] + sortedZahlen[NUM_ELEMENTS / 2]) / 2.0;
  } else {
    median = sortedZahlen[NUM_ELEMENTS / 2];
  }

  Serial.print("Median: ");
  Serial.println(median);
}

void loop() {
}

void sortArray(int arr[], int size) {
  for (int i = 0; i < size - 1; i++) {
    for (int j = 0; j < size - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        int temp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = temp;
      }
    }
  }
}
