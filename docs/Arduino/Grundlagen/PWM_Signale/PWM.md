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

\documentclass{article} \usepackage{amsmath}

\begin{document}

\title{PWM Signale mit Arduino} \author{} \date{} \maketitle

\section*{Fragen und Antworten}

\begin{enumerate} \item Mit dem folgenden Befehl wird ein PWM-Signal erzeugt:
\texttt{analogWrite(9, 201)}. Bestimmen Sie das Tastverhältnis des PWM-Signals
in Prozent. \begin{equation*} n = \frac{201}{255} \times 100 \approx 78.82\%
\end{equation*} \item Welchen Wert muss der Parameter für das Tastverhältnis in
der Funktion \texttt{analogWrite()} annehmen, damit sich ein Tastverhältnis von
80\% ergibt? \begin{equation*} \text{Wert} = 255 \times 0.8 = 204
\end{equation*} \item Schreiben Sie ein Programm, welches per Tastendruck die
Helligkeit einer LED in 6 Stufen ändert. \item Ergänzen Sie Ihr Programm so,
dass die LED beim Erreichen der maximalen Helligkeit zweimal kurz blinkt und
beim nächsten Tastendruck wieder schrittweise in der Helligkeit geändert werden
kann. \item Die Helligkeit einer LED soll sich wiederkehrend von Aus auf
maximale Helligkeit und anschließend wieder auf Aus ändern (Fading). \item
Schreiben Sie ein Programm für ein futuristisches Lauflicht mit 6 LEDs, bei dem
zu jedem Zeitpunkt immer zwei bis drei LEDs mit verschiedenen Helligkeitswerten
leuchten. Die erste LED soll möglichst hell und die nachfolgenden LEDs etwas
dunkler leuchten. Das Lauflicht soll kontinuierlich hin- und herwandern.
\end{enumerate}

\end{document}