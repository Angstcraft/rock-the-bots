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

\documentclass[a4paper,12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage{amsmath}
\usepackage{graphicx}
\usepackage{listings}
\usepackage{fancyhdr}
\usepackage{geometry}

% Defining geometry of the document
\geometry{top=2cm, bottom=2cm, left=2cm, right=2cm}

\title{Analyse von IR-Photodetektoren}
\author{Ihr Name}
\date{\today}

\begin{document}

\maketitle

\section*{Einleitung}
In dieser Arbeit werden die Eigenschaften und Anwendungen von Infrarot-Photodetektoren, insbesondere von Photodioden und Phototransistoren, untersucht. Ziel ist es, verschiedene Lichtspektren zu recherchieren, den Kollektorstrom zu messen und ein einfaches Arduino-Programm zu erstellen.

\section*{Aufgabe 1}
Recherchieren Sie die Lichtspektren verschiedener Lichtquellen und vergleichen Sie diese mit der spektralen Empfindlichkeit des Phototransistors PT 333-3C:

\begin{enumerate}
    \item[a)] Sonne (Tageslicht)
    \item[b)] LED-Lampe
    \item[c)] Leuchtstoffröhre
    \item[d)] Glühlampe
\end{enumerate}

\textbf{Antwort:} Die Lichtquellen haben unterschiedliche Spektren. Die Sonne hat ein kontinuierliches Spektrum mit vielen Wellenlängen, während LEDs meist nur über spezifische Wellenlängen emittieren. Leuchtstoffröhren zeigen ebenfalls Peaks bei bestimmten Wellenlängen und Glühlampen bieten ein kontinuierliches Spektrum, jedoch mit mehr Energie im infraroten Bereich.

\section*{Aufgabe 2}
Messen Sie mit einem Multimeter den Kollektorstrom des Phototransistors, wenn dieser eine Kollektor-Emitter-Spannung von 5 V aufweist. \\
Welcher Kollektorstrom ergibt sich bei direkter und indirekter (Reflexion) Einstrahlung vom IR-Licht der IR-LED? ( RV ≈ 220 Ω)

\textbf{Antwort:} 
Um den Kollektorstrom zu berechnen, kann das Ohm'sche Gesetz verwendet werden:
\[
I_C = \frac{U_C}{R_M}
\]
Dabei ist \( U_C \) die Kollektor-Emitter-Spannung und \( R_M \) der Messwiderstand.

\section*{Aufgabe 3}
Der maximale Kollektorstrom eines Phototransistors sei 1 mA. Schätzen Sie den benötigten Messwiderstand rechnerisch so ab, dass die Maximalspannung am Analogeingang des Arduino 5V beträgt (Schaltung).

\textbf{Antwort:} 
Zur Bestimmung des Messwiderstands \( R_M \), setzt man \( I_C = 1~\text{mA} \):
\[
U = I_C \times R_M \\
R_M = \frac{U}{I_C} = \frac{5~\text{V}}{1~\text{mA}} = 5~\text{kΩ}
\]

\section*{Aufgabe 4}
Bauen Sie den IR-Sensor mit Phototransistor und IR-LED ( RV ≈ 220 Ω) auf einem Steckbrett auf. Lesen Sie mit dem Analogeingang des Arduinos die Spannung am Messwiderstand RM ≈ 5 kΩ ein.

\textbf{Hinweis:} Stellen Sie sicher, dass Sie eine geeignete Schaltung aufbauen.

\section*{Aufgabe 5}
Schreiben Sie ein Programm, das auf dem seriellen Plotter die Spannung am Messwiderstand ausgibt.

\begin{lstlisting}[language=C]
void setup() {
    Serial.begin(9600);
}

void loop() {
    int sensorValue = analogRead(A0);
    float voltage = sensorValue * (5.0 / 1023.0);
    Serial.println(voltage);
    delay(100);
}
\end{lstlisting}

\section*{Aufgabe 6}
Erweitern Sie die Schaltung aus Aufgabe 4 um eine LED. Die LED soll leuchten, wenn der Sensor:

\begin{enumerate}
    \item ein weißes Blatt erkennt,
    \item eine schwarze Linie auf dem Blatt erkennt.
\end{enumerate}

\textbf{Hinweis:} Bestimmen Sie durch Probieren den Schwellwert zum Erkennen des Blattes bzw. der schwarzen Linie.

\section*{Aufgabe 7}
Analysieren Sie den Einfluss der Lage der IR LED und des Phototransistors bezüglich der Empfindlichkeit des Sensors, eine schwarze Linie zu detektieren. Welchen Einfluss hat der Abstrahlwinkel, die Höhe und der Abstand zwischen LED und Phototransistor?

\textbf{Antwort:} Der Abstrahlwinkel der LED beeinflusst die Intensität des Lichtes, das auf den Phototransistor trifft. Ein kleiner Abstand erhöht die Empfindlichkeit, während eine zu große Höhe oder ein ungünstiger Winkel das Signal reduzieren kann.

\end{document}