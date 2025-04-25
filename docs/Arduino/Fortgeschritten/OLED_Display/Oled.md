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

\documentclass{article} \usepackage[utf8]{inputenc} \usepackage{graphicx}
\usepackage{verbatim} \usepackage{amsmath}

\title{OLED Display} \author{} \date{}

\begin{document}

\maketitle

\section*{OLED SSD1306} \textbf{(OLED SSD1306 mit 0.96 oder 1.3 Zoll und 128×64
Pixeln)}

Das SSD1306 OLED Display mit I2C Schnittstelle kann ohne weitere Bauteile
direkt an den Arduino angeschlossen werden. Es gelten folgende Belegungen:

\begin{center} \begin{tabular}{|c|c|} \hline \textbf{OLED mit I2C} &
\textbf{Arduino UNO} \\ \hline GND & GND \\ VCC & 5V \\ SCL & SCL (oder A5) \\
SDA & SDA (oder A4) \\ \hline \end{tabular} \end{center}

Für die einfache Textausgabe sollte die gut dokumentierte U8g2 Bibliothek über
den Arduino Bibliotheksmanager eingebunden werden.

Der Konstruktor für die 0.96 Zoll Variante des OLED Displays ist wie folgt:

\begin{verbatim} U8X8_SSD1306_128X64_NONAME_HW_I2C u8x8(U8X8_PIN_NONE);
\end{verbatim}

\subsection*{Einfache Textausgabe} Hier ist ein Beispiel-Link für ein Projekt:
\texttt{https://wokwi.com/projects/353733080329208833}

\begin{verbatim} #include <Arduino.h> #include <U8x8lib.h> // Bibliothek U8g2
einbinden

// Beim Arduino Uno werden folgende Pins für das OLED Display verwendet // OLED
Arduino UNO // ----- ------------- // GND GND // VCC 5V // SCL SCL (oder A5) //
SDA SDA (oder A4)

// Konstruktur für I2C OLED 0,96 mit 4 Pins (ohne Reset Pin)
U8X8_SSD1306_128X64_NONAME_HW_I2C u8x8(U8X8_PIN_NONE);

void setup(void) { u8x8.begin(); //u8x8.setFont(u8x8_font_chroma48medium8_r);
u8x8.setFont(u8x8_font_artossans8_r); // Schriftart auswählen u8x8.drawString(3,
3, "Hallo Welt !"); delay(2000); }

void loop(void) { u8x8.clear(); // Löscht das Display u8x8.setInverseFont(0);
// weiß auf schwarzem Hintergrund u8x8.drawString(0, 0, "(0,0)"); // Gibt einen
Text an der Stelle (x,y) aus u8x8.drawString(10, 0, "(10,0)"); // (10,0) ist
rechts oben

u8x8.setInverseFont(1); // schwarz auf weißem Hintergrund u8x8.drawString(0, 7,
"(0,8)"); // (0,8) ist links unten u8x8.drawString(10, 7, "(10,8)"); // (10,8)
ist rechts unten delay(2000); u8x8.setInverseFont(0); u8x8.clear(); for (int z =
0; z < 8; z++) { u8x8.setCursor(0, z); // setzt den Cursor an die Stelle (x,y)
u8x8.print("Z"); // Gibt Text aus u8x8.print(z); u8x8.print(":"); for (int i = 0;
i < (z * 2)-1; i++) { u8x8.print("."); delay(100); } } delay(1000);

for (int z = 7; z >= 0; z--) { u8x8.clearLine(z); // Löscht die angegebene
Zeile delay(100); } delay(1000); } \end{verbatim}

Die einzelnen Befehle der Bibliothek sind in der Referenz gut erläutert. Zum
Beispiel \texttt{print} oder \texttt{drawString}.

\subsection*{Terminal mit Zeilenvorschub} Hier ist ein Beispiel-Link für ein
weiteres Projekt: \texttt{https://wokwi.com/projects/353732054698049537}

\begin{verbatim} #include <Arduino.h> #include <U8x8lib.h> // Bibliothek U8g2
einbinden

// Konstruktur für I2C OLED 0,96 mit 4 Pins (ohne Reset Pin) // Beim Arduino
Uno werden folgende Pins für das OLED Display verwendet // OLED Arduino UNO //
----- ------------- // GND GND // VCC 5V // SCL SCL (oder A5) // SDA SDA (oder
A4)

U8X8_SSD1306_128X64_NONAME_HW_I2C u8x8(U8X8_PIN_NONE); // Die Größe des OLED 0.
96 Displays #define U8LOG_WIDTH 16 #define U8LOG_HEIGHT 8

// Konfigurieren des Terminals (U8X8LOG) uint8_t
u8log_buffer[U8LOG_WIDTH*U8LOG_HEIGHT]; U8X8LOG u8x8log;

void setup(void) { u8x8.begin(); u8x8.setFont(u8x8_font_chroma48medium8_r);
u8x8log.begin(u8x8, U8LOG_WIDTH, U8LOG_HEIGHT, u8log_buffer); u8x8log.
setRedrawMode(1); // 0: Update screen with newline, // 1: Update screen for
every char }

unsigned long t = 0; // Gibt das Ergebnis von millis() dem Display aus void
loop(void) { if ( t < millis() ) { t = millis() + 10000; // alle 10 Sekunden
u8x8log.print("\f"); // \f = form feed: Löscht das Display } u8x8log.
print("millis="); u8x8log.print(millis()); u8x8log.print("\n"); delay(20); }
\end{verbatim}

\end{document}