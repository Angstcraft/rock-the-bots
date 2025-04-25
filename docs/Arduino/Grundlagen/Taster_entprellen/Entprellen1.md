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

//Entschuldigung fuer Rechschreib Fehlern.
//Habe nochmal mit deepl für ein paar form definiionen ruebergeschaut hoffe es sind nicht mehr.

\documentclass[a4paper,10pt]{article} \usepackage[utf8]{inputenc}
\usepackage{amsmath} \usepackage{graphicx} \usepackage{hyperref}

\title{Erläuterung zur Notwendigkeit der Zustandsüberprüfung nach der
Prellzeit} \author{} \date{}

\begin{document}

\maketitle

\section{Erläuterung zur Notwendigkeit der Zustandsüberprüfung}

Nach der Prellzeit ist es notwendig, den Zustand des Tasters erneut zu
überprüfen, weil der Taster beim Drücken möglicherweise nur für einen kurzen
Moment prellt. Dies bedeutet, dass die Kontakte des Tasters während des Drückens
mehrere schnelle Zustandsänderungen durchlaufen können.

\subsection{Beispiel}

Stellen Sie sich vor, dass der Taster in einem Zustand von HIGH (nicht
gedrückt) zu LOW (gedrückt) wechselt. Während des Betätigens kann es zu
Störungen kommen, die dazu führen, dass der Zustand zusätzlich mehrfach zwischen
HIGH und LOW wechselt, bevor er stabil auf LOW bleibt. Wenn wir nach der ersten
Zeiterfassung (zum Beispiel am Anfang der Prellzeit) die Statusänderung nicht
erneut überprüfen, könnte es passieren, dass wir eine Aktion ausführen, die
nicht dem tatsächlichen Zustand des Tasters entspricht.

\subsection{Folgen}

Wenn der Zustand nach der Prellzeit nicht erneut überprüft wird und einer der
vorangegangenen Zustände für die Logik der Programmierung ausschlaggebend ist,
könnte es zu unerwarteten Ergebnissen kommen. Beispielsweise könnte eine
angeschlossene LED versehentlich ein- oder ausgeschaltet werden, obwohl der
Taster tatsächlich nicht mehr gedrückt war. Daher stellen wir mit einer erneuten
Überprüfung sicher, dass der Taster tatsächlich im gewünschten Zustand
(\textit{gedrückt}) verbleibt, bevor wir die entsprechende Aktion ausführen.

\end{document}