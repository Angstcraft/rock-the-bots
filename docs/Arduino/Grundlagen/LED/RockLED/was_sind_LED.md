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

\documentclass{article} \usepackage[utf8]{inputenc} \usepackage{enumitem}

\begin{document}

\section*{Aufgaben}

\begin{enumerate}[label=\alph*)] \item Recherchieren Sie die üblichen
Diodenspannungen \( U_D \) verschiedenfarbiger LEDs: \begin{itemize} \item a)
Rot: \( U_D \approx 2 \, \text{V} \) \item b) Gelb: \( U_D \approx 2.1 \,
\text{V} \) \item c) Grün: \( U_D \approx 2.2 \, \text{V} \) \item d) Blau: \(
U_D \approx 3.0 \, \text{V} \) \item e) Weiß: \( U_D \approx 3.0 - 3.5 \,
\text{V} \) \end{itemize} \item Bestimmen Sie für eine an 5 V angeschlossene
blaue LED den benötigten Vorwiderstand, damit ein Maximalstrom von 20 mA bei
einer Spannung von 3,2 V nicht überschritten wird: Gegeben: \begin{itemize}
\item \( U_0 = 5 \, \text{V} \) \item \( U_D = 3.2 \, \text{V} \) \item \( I_D =
20 \, \text{mA} = 0.02 \, \text{A} \) \end{itemize} Widerstandsberechnung: \[
R_V = \frac{U_0 - U_D}{I_D} = \frac{5 \, \text{V} - 3.2 \, \text{V}}{0.02 \,
\text{A}} = \frac{1.8 \, \text{V}}{0.02 \, \text{A}} = 90 \, \Omega \]

\item Zwei rote LEDs mit einer Diodenspannung von 2 V und einem Strom von 20
mA werden in Reihe an 5 V angeschlossen. Zeichnen Sie die Schaltung mit
Vorwiderstand. Bestimmen Sie den Wert des Vorwiderstandes \( [50 \, \Omega] \):
Gegeben: \begin{itemize} \item \( U_0 = 5 \, \text{V} \) \item \( U_D = 2 \,
\text{V} \) (für jede LED) \item Anzahl der in Reihe geschalteten LEDs: 2 \item
\( I_D = 20 \, \text{mA} \) \end{itemize} Widerstandsberechnung: \[ U_D
(\text{für 2 LEDs}) = 2 \cdot 2 \, \text{V} = 4 \, \text{V} \] \[ R_V =
\frac{U_0 - U_D}{I_D} = \frac{5 \, \text{V} - 4 \, \text{V}}{0.02 \, \text{A}} =
\frac{1 \, \text{V}}{0.02 \, \text{A}} = 50 \, \Omega \]

\item Eine ultrahelle LED mit folgendem Datenblatt soll an eine
Spannungsquelle mit 5 V angeschlossen werden. Bestimmen Sie den nötigen
Vorwiderstand, damit die Stromaufnahme der LED 50 mA beträgt \( [58 \, \Omega]
\): Gegeben: \begin{itemize} \item \( U_0 = 5 \, \text{V} \) \item \( U_D = 3 \,
\text{V} \) (angenommener Wert) \item \( I_D = 50 \, \text{mA} = 0.05 \,
\text{A} \) \end{itemize} Widerstandsberechnung: \[ R_V = \frac{U_0 - U_D}{I_D}
= \frac{5 \, \text{V} - 3 \, \text{V}}{0.05 \, \text{A}} = \frac{2 \,
\text{V}}{0.05 \, \text{A}} = 40 \, \Omega \, \text{(niedriger als angenommen)}
\]

\end{enumerate}

\end{document}