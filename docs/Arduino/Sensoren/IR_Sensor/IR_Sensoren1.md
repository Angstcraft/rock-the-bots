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

\documentclass[a4paper,11pt]{article} \usepackage[utf8]{inputenc}
\usepackage{amsmath} \usepackage{graphicx}

\title{Analyse von IR-Sensoren und der IR-LED TSAL6100} \author{} \date{}

\begin{document}

\maketitle

\section{Grundprinzip eines IR-Sensors}

Der Infrarotsensor (IR-Sensor) basiert auf dem Prinzip der Reflexion von Licht.
Dieser Sensor sendet Infrarotlicht aus, welches auf Objekte trifft und
reflektiert wird. Ein Empfänger detektiert die Intensität des reflektierten
Lichtes.

Die Intensität des vom Empfänger aufgenommenen Lichtes hängt von folgenden
Faktoren ab: \begin{itemize} \item \textbf{Abstand}: Der Abstand zwischen dem
Sensor und der reflektierenden Oberfläche beeinflusst die Lichtintensität. Ist
der Abstand größer, ist die empfangene Lichtintensität geringer. \item
\textbf{Oberflächenbeschaffenheit}: Glatte und helle Oberflächen reflektieren
mehr Licht als raue oder dunkle Oberflächen. \item \textbf{Farbe der Oberfläche}:
Unterschiedliche Farben reflektieren Licht unterschiedlich stark. Helle Farben
reflektieren in der Regel mehr Infrarotlicht als dunkle. \item
\textbf{Einfallwinkel}: Der Winkel, in dem das Licht auf die Oberfläche trifft,
beeinflusst ebenfalls die reflektierte Intensität. \end{itemize}

IR-Sensoren sind geeignet zur Hinderniserkennung oder Linienverfolgung. Sie
sind weniger geeignet zur präzisen Entfernungsbestimmung, da die reflektierte
Lichtintensität nicht linear mit dem Abstand variiert und durch
Umgebungslichtquellen beeinflusst werden kann.

\section{Datenblattanalyse der IR-LED TSAL6100}

\subsection{Besondere Eigenschaften der LED} Die IR-LED TSAL6100 zeichnet sich
durch folgende Eigenschaften aus: \begin{itemize} \item Wellenlänge von etwa 940
nm, optimiert für Infrarot-Anwendungen. \item Hohe Effizienz und Leistung. \item
Robuste Bauweise für den industriellen Einsatz. \end{itemize}

\subsection{Typische Anwendungen der LED} Die typischen Anwendungen der
TSAL6100 sind: \begin{itemize} \item Fernsteuerungen. \item Infrarotsensoren für
Hindernis- und Linienverfolgung. \item Optische Datenübertragung. \end{itemize}

\subsection{Maximaler Vorwärtsstrom der LED} Der maximale Vorwärtsstrom
(forward current) der LED beträgt 1000 mA, jedoch sollte sie in der Regel bei
einem deutlich niedrigeren Strom betrieben werden.

\subsection{Maximale Leistungsaufnahme der LED} Die maximale Leistungsaufnahme
(power dissipation) der LED beträgt etwa 1000 mW.

\subsection{Richtcharakteristik} Die Richtcharakteristik der TSAL6100 zeigt
eine ausgeprägte Konzentration des abgestrahlten Lichts in einem bestimmten
Winkelbereich. Der Abstrahlwinkel beträgt in der Regel etwa 20 bis 30 Grad,
wodurch das Licht in einem relativ schmalen Kegel abgestrahlt wird.

\section{Durchmesser des ausgeleuchteten Bereichs am Boden}

Die IR-LED befindet sich 5 cm senkrecht über dem Boden. Um den Durchmesser des
ausgeleuchteten Bereichs am Boden zu berechnen, verwenden wir den Öffnungswinkel
von 20 Grad.

Der Durchmesser \(D\) kann mit folgender Formel berechnet werden:

\[ D = 2 \cdot (h \cdot \tan(\frac{\theta}{2})) \]

Dabei ist: \begin{itemize} \item \(h = 5 \ \text{cm}\) (Höhe der LED) \item
\(\theta = 20^\circ\) (Öffnungswinkel) \end{itemize}

Einsetzen der Werte:

\[ D = 2 \cdot (5 \cdot \tan(10^\circ)) \approx 2 \cdot (5 \cdot 0.1763)
\approx 1.763 \ \text{cm} \]

\section{Berechnung des Vorwiderstands der IR-LED}

Um den Vorwiderstand \(R\) der IR-LED zu bestimmen, so dass der Diodenstrom
\(I\) 20 mA nicht übersteigt, verwenden wir das Ohm'sche Gesetz:

\[ R = \frac{U_{vs} - U_{LED}}{I} \]

Dabei sind: \begin{itemize} \item \(U_{vs} = 5 \ \text{V}\)
(Versorgungsspannung) \item \(U_{LED} \approx 1.2 \ \text{V}\)
(Durchlassspannung der LED) \item \(I = 0.02 \ \text{A}\) (Diodenstrom)
\end{itemize}

Einsetzen der Werte:

\[ R = \frac{5 - 1.2}{0.02} = \frac{3.8}{0.02} = 190 \ \Omega \]

Der Vorwiderstand sollte also \textbf{190 Ohm} betragen, um einen Diodenstrom
von 20 mA nicht zu überschreiten.

\end{document}