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

Kopieren Sie des Beispielprogramm und lassen sie es auf Ihrem Arduino mit der entsprechenden Schaltung laufen. Untersuchen Sie, was passiert, wenn einige der break-Anweisung auskommentiert (// ) werden. Wie verhält sich dann Ihr Programm?

Zeichnen Sie ein Zustandsdiagramm für den Automaten mit zwei LEDs, bei dem folgende Übergänge bzw. Zustände erlaubt sind. Nach dem letzten Zustand springt der Automat in der ersten Zustand zurück.

alle Leds aus → Led 1 an, Led 2 aus → alle Leds aus → Led 1&2 an → alle LEDs aus → Led 2 an, Led 1 aus → . . .

Schreiben Sie ein Programm für den obigen Automaten und testen Sie es an einer entsprechenden Schaltung.

Ändern Sie das Programm für den ursprünglichen Automaten mit 2 LEDs so, dass für jeden der vier Zustände ein eigenes Zeitintervall (dTime1, dTime2,...) angegeben werden kann, in welchem er aktiv ist. Oder anders ausgedrückt, jeder der vier Zustände soll unterschiedlich lange aktiv sein.

Programmieren Sie einen Reaktionstester. Bauen Sie dafür zuerst eine Schaltung mit zwei Tastern und zwei verschiedenfarbigen LEDs auf. Implementieren Sie folgendes Verhalten:

    Als Indikator, das der Test beginnen kann, leuchtet zu Beginn die LED 1 und auf dem seriellen Monitor wird folgender Text ausgegeben:

    -------------------------------
    Reaktionstester bereit!

Anschließend wird der Taster S1 gedrückt. Auf dem seriellen Monitor erscheint der Text:

Warten auf das rote Licht ...

Jetzt wird gewartet bis die LED 2 aufleuchtet.

Nach einer zufälligen Zeit leuchtet die LED 2 auf und die LED 1 fängt an schnell zu blinken. Von diesem Zeitpunkt wird die Zeit gemessen, bis der Taster 2 betätigt wird.

Sobald der Taster 2 gedrückt wurde, erlischt die LED 1 und auf dem seriellen Monitor wird die Reaktionszeit in Sekunden angegeben:

Reaktionszeit: 1,23 Sekunden
-------------------------------

Zeichnen Sie das Zustandsdiagramm für eine einfache Autoampel (mit den Bedingungen für die Zustandsübergänge). Für die Zeiten der einzelnen Ampelphasen gilt:

    ROT: 3 Sekunden
    ROT-GELB: 0.5 Sekunden
    GRÜN: 3 Sekunden
    GELB: 1 Sekunde

Bauen Sie anschließend eine geeignete Schaltung auf und programmieren Sie mit der switch-case Anweisung und dem enum Datentyp den endlichen Automaten für die Ampel.

Entwickeln Sie ein Programm und eine elektrische Schaltung zur Simulation einer Ampelanlage für Fußgänger (eine Fußgängerampel FA und eine Ampel für PKWs PA). Ähnlich wie bei echten Ampelanlagen für Fußgänger, darf die Fußgängerampel erst nach dem Betätigen eines Tasters (Anforderung durch einen Fußgänger) und einer gewissen Wartezeit auf Grün umschalten. Beachten Sie bei der Bearbeitung der Aufgabe folgende Punkte:

    Erstellen Sie ein vollständiges Zustandsdiagramm für beide Ampeln. Recherchieren Sie die möglichen Zustände der Ampeln und benennen Sie diese sinnvoll (FArot, FAgruen, PArot, ...). Geben Sie im Zustandsdiagramm alle Zustände und Bedingungen für die Zustandsübergänge korrekt an.
    Entwickeln Sie eine Schaltung für die Ampelanlage. Zeichnen Sie Ihre Schaltung auf und bauen Sie sie anschließend auf dem Steckbrett auf. Vergessen Sie nicht den Taster für die Fußgängeranforderung.
    Schreiben Sie ein Programm, welches ihr Zustandsdiagramm umsetzt. Verwenden Sie die switch-case-Anweisung.