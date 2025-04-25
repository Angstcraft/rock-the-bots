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

\documentclass{article} \usepackage[utf8]{inputenc} \usepackage{amsmath}

\title{Aufgabe 1 und 2} \author{} \date{}

\begin{document}

\maketitle

\section*{1. Unterschied zwischen Deklaration, Zuweisung und Initialisierung}

\begin{itemize} \item \textbf{Deklaration:} Bei der Deklaration wird eine
Variable in einem Programm definiert. Dabei wird der Variablenname und der
Datentyp festgelegt, aber es erfolgt noch keine Zuweisung eines Wertes.
\begin{itemize} \item \textit{Beispiel:} \begin{verbatim} int pinLed; %
Deklaration der Variable pinLed mit dem Datentyp int \end{verbatim}
\end{itemize} \item \textbf{Zuweisung:} Die Zuweisung ist der Prozess, bei dem
einer bereits deklarierten Variable ein Wert zugewiesen wird. \begin{itemize}
\item \textit{Beispiel:} \begin{verbatim} pinLed = 12; % Zuweisung des Wertes 12
an die Variable pinLed \end{verbatim} \end{itemize}

\item \textbf{Initialisierung:} Die Initialisierung ist eine Kombination aus
Deklaration und Zuweisung. Sie legt die Variable und den Wert gleichzeitig fest,
sodass die Variable mit einem Anfangswert versehen wird. \begin{itemize} \item
\textit{Beispiel:} \begin{verbatim} int pinLed = 12; % Deklaration und
Initialisierung der Variable pinLed \end{verbatim} \end{itemize} \end{itemize}

\section*{2. Datentypen zur Speicherung bestimmter Werte}

Die Werte, die Sie nennen, können in den folgenden Datentypen gespeichert
werden:

\begin{itemize} \item \textbf{1:} \texttt{int}, \texttt{long}, \texttt{unsigned
int}, \texttt{float}, \texttt{double} \item \textbf{2.0:} \texttt{float},
\texttt{double} \item \textbf{14.35:} \texttt{float}, \texttt{double} \item
\textbf{-2365:} \texttt{int}, \texttt{long}, \texttt{signed int}, \texttt{float},
\texttt{double} \item \textbf{67542:} \texttt{int}, \texttt{long},
\texttt{unsigned int}, \texttt{float}, \texttt{double} \item \textbf{-34543:}
\texttt{int}, \texttt{long}, \texttt{signed int}, \texttt{float},
\texttt{double} \end{itemize}

\end{document}