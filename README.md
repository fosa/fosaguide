# fosaguide

Grundregeln für die Arbeit an FOSA

Achtung! Diese Regeln sind noch nicht definitiv und werden noch überarbeitet! 

## Grundlegende Code-Regeln
 - Zeilenlänge auf (maximal) 80 Zeichen begrenzen
 - Das Encoding ist UTF-8
 - Eigene Datei für neues Kapitel
 - Labels verwenden: 
  - \label{fig:...} für Grafiken
  - \label{sec:...} für Kapitel und Unterkapitel
  - \label{tab:...} für Tabellen
  - \label{sch:...} für Schemen

## Workflow
### Core-Developer
Da Core-Developer Commit-Rechte auf das Repository haben, müssen diese 
strukturiert arbeiten. Um Redundanzen und Merge-Konflikte zu vermeiden wird 
stets gegen Issues gearbeitet und wenn möglich eines nach dem anderen.

 - Issue erstellen falls noch nicht vorhanden
 - Issue assignen
 - Branch erstellen (für länger dauernde oder grössere Arbeiten)
 - Lokal testen und builden
 - nach erfolgreichem build pushen 
 - Falls Issue abgeschlossen pushen mit issue-tag wie "close #33"

### Allgemeine Contributor
Da beliebige Contributor keine Push-Rechte auf das Repository haben gehen 
diese wie auf Github üblich vor.

 - Repository forken
 - Patch erstellen
 - Pull-Request machen (vorzugsweise über Github, nicht per git)

## Spezifische Code-Regeln

### Umlaute
 - NIE in Dateinamen verwenden
 - NIE für Labels, Referenzen verwenden (\label{}, \ref{})
 - Im Code als UTF-8 Zeichen schreiben (nicht \" verwenden)

### Dateinamen
 - Grundsätzlich Lowercase verwenden
 - Grundsätzlich "-" Verbinder (CamelCase akzeptiert)

### Tabellen
 - Tabellen auch im Code strukturieren
 - Horizontale Linien wo möglich vermeiden
  - Wo Hervorhebung nötig Schattierungen verwenden (mit lgray und white)
 - Vertikale Linien wo möglich vermeiden

### Grafiken
 - Eigener Ordner für Grafiken
 - Vektorgrafiken verwenden (EPS, PDF (SVG)) 
 - Falls Bitmap gleich ein Issue erstellen (JPG, PNG) zur Änderung
 - Grundsätzlich selbst erstellt (Tipp: Inkscape)
  - Fremde Inhalte im Code vermerken mit Quellenverweis (ggf. auch im Output)
  - Lizenzen fremder Inhalte beachten und freie vorziehen (wenn möglich cc)

### Struktur
Jede Fosa hat die gleiche Struktur welche die folgenden Elemente enthält.

#### /

	README.md
	LICENSE
	.gitignore

Optional

	makefile
	"helper-skript".sh
	
#### /tex

	"name-der-fosa".tex
	"name-des-kapitels".tex
	...

Optional

	literatur.bib
	glossar.tex
	...

#### /fig
Selbsterstellte Vektorgrafiken immer mit Originalformat (z.B. SVG) ablegen.
	
	template.svg
	template.eps
	template.pdf

	"treffender-name".eps
	"treffender-name".pdf
	"treffender-name".svg

#### /ext
Manchmal möchte oder muss man Fremdinhalte einbinden. Diese sind separiert.

	"fremde-inhalte".pdf
	...

## FOSA-Tags

Um die Kollaboration zu vereinfachen gibt es die FOSA-Tags.

### Beispiele

#### Bild einfügen

	... hat einen Knick im Graphen (siehe Grafik \ref{fig:knick}).
	
	\begin{figure}
		\centering
		>>>FOSA: hier Plot einfügen
		\caption{Graph mit einem Knick}
		\label{fig:knick}
	\end{figure}

