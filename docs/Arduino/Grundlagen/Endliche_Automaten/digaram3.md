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


\documentclass{article} \usepackage{tikz} \usetikzlibrary{arrows, positioning}

\begin{document}

\begin{center} \begin{tikzpicture}[ state/.style={rectangle, draw, minimum
width=2.5cm, minimum height=1cm}, arrow/.style={->, thick} ]

% Define states \node[state] (rot) {ROT}; \node[state, below=of rot] (rotgelb)
{ROT-GELB}; \node[state, below=of rotgelb] (gruen) {GRÜN}; \node[state, below=of
gruen] (gelb) {GELB};

% Define arrows \draw[arrow] (rot) -- (rotgelb); \draw[arrow] (rotgelb) --
(gruen); \draw[arrow] (gruen) -- (gelb);

\end{tikzpicture} \end{center}

\end{document}