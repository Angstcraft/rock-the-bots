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

\documentclass[a4paper,12pt]{article} \usepackage[utf8]{inputenc}
\usepackage{amsmath} \usepackage{graphicx} \usepackage{hyperref}

\title{Aufgaben zum Gleichstrommotor} \author{} \date{}

\begin{document}

\maketitle

\section{Aufgabe 1: Maximale Stromaufnahme} Ein einfacher Gleichstrommotor wird
mit vier in Reihe geschalteten 1,5 Volt Batterien betrieben. Die Maximalspannung
der neuen Batterien beträgt 1,58 V. Der Wicklungswiderstand beträgt \( R = 5 \,
\Omega \).

Die Gesamtspannung \( U \) der Batterien beträgt: \[ U = 4 \times 1.58 \, V = 6.
32 \, V \]

Der maximale Strom \( I_{\text{max}} \) kann durch Ohm'sches Gesetz berechnet
werden: \[ I_{\text{max}} = \frac{U}{R} = \frac{6.32 \, V}{5 \, \Omega} = 1.264
\, A \]

Für den Motor muss also mit einer maximalen Stromaufnahme von \( 1.264 \, A \)
gerechnet werden.

\section{Aufgabe 2: Maximale Betriebszeit der Motoren} Die zwei Motoren eines
einfachen Roboters werden mit vier in Reihe geschalteten 1,5 Volt Batterien
betrieben, welche am Anfang eine Energie (pro Batterie) von 2,7 Wh gespeichert
haben. Die Stromaufnahme jedes einzelnen Motors beträgt im Mittel 350 mA und die
über die Zeit gemittelte Spannung der einzelnen Batterien beträgt 1,2 Volt.

Die Gesamtenergie der Batterien beträgt: \[ E_{\text{total}} = 4 \times 2.7 \,
\text{Wh} = 10.8 \, \text{Wh} \]

Die Stromaufnahme für beide Motoren ist: \[ I_{\text{total}} = 2 \times 0.350 \,
A = 0.700 \, A \]

Um die maximale Betriebszeit \( t \) zu berechnen, verwenden wir die Formel: \[
t = \frac{E_{\text{total}}}{U \cdot I_{\text{total}}} \] wobei \( U \) die
gemittelte Spannung von 1,2 V ist: \[ t = \frac{10.8 \, \text{Wh}}{1.2 \, V
\cdot 0.700 \, A} = \frac{10.8}{0.84} \approx 12.86 \, \text{h} \]

Die maximale Betriebszeit der beiden Motoren beträgt also ca. \( 12.86 \,
\text{h} \).

\section{Aufgabe 3: Gefahren eines blockierenden Motors} Ein Elektromotor
sollte nicht blockiert werden, da dies zu verschiedenen Problemen führen kann:
\begin{itemize} \item \textbf{Überhitzung:} Der Motor kann überhitzen, da der
Strom bei blockiertem Zustand auf das maximale Maß ansteigt, was die Wicklungen
und die Isolierung schädigen kann. \item \textbf{Mechanische Beschädigung:}
Blockierung kann dazu führen, dass mechanische Teile brechen oder sich verformen.
\item \textbf{Sicherheitsrisiko:} Ein blockierter Motor kann ein
Sicherheitsrisiko darstellen, insbesondere wenn andere Teile des Roboters
weiterhin bewegen oder reagieren. \end{itemize}

\section{Aufgabe 4: Beobachtungen beim Handdrehen des Motors} Beim Schließen
der Kontakte des Motors und dem Drehen des Motors per Hand kann Folgendes
beobachtet werden: \begin{itemize} \item \textbf{Mit geschlossenen Kontakten:}
Der Motor verhält sich wie ein Generator und erzeugt eine Gegenspannung, was
bedeutet, dass beim Drehen der Motor sich mehr Widerstand bietet. \item
\textbf{Mit offenen Kontakten:} Hier wird festgestellt, dass es keinen
Widerstand gibt, der Motor lässt sich leicht drehen, da kein aktueller Fluss
stattfindet. \end{itemize}

Diese Beobachtungen lassen sich mit Hilfe der Ersatzschaltung erklären:
\begin{itemize} \item Im geschlossenen Zustand wird der Motor durch seine
Wicklungen und den erzeugten Strom, als Generator betrachtet, in seiner Bewegung
gehemmt (Gegenspannung wirkt). \item Mit offenen Kontakten gibt es keine
elektrischen Elemente, die den Motor in seiner Bewegung stören würden.
\end{itemize}

\end{document}