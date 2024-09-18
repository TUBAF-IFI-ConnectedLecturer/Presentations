<!--
author:   Sebastian Zug; André Dietrich

email:    sebastian.zug@informatik.tu-freiberg.de

version:  0.1.2

language: en

narrator: UK English Female

icon:     https://media.aubi-plus.com/institution/thumbnail/3f3de48-technische-universitaet-bergakademie-freiberg-logo.jpg

link:     style.css

import:   https://raw.githubusercontent.com/liaTemplates/ABCjs/main/README.md
          https://raw.githubusercontent.com/liaTemplates/AVR8js/main/README.md

          https://raw.githubusercontent.com/LiaScript/CodeRunner/master/README.md
          https://raw.githubusercontent.com/liascript-templates/plantUML/master/README.md
          https://raw.githubusercontent.com/liaScript/mermaid_template/master/README.md

mark
  <span style="background-color: @0;
                           display: flex;
                           width: calc(100% + 32px);
                           margin: -16px;
                           padding: 6px 16px 6px 16px;
                           ">@1</span>
@end                           

red:  @mark(#FF888888,@0)

-->

[![LiaScript](https://raw.githubusercontent.com/LiaScript/LiaScript/master/badges/course.svg)](https://liascript.github.io/course/?https://raw.githubusercontent.com/TUBAF-IFI-ConnectedLecturer/Presentations/main/Wel2024/Presentation.md)

# OER – Connected Lecturers

<h2>Projektziele und Status der Umsetzung</h2>

---

| Partner an der TUBAF                      | Projektbeteiligte             |
| ----------------------------------------- | ----------------------------- |
| Lehrstuhl Softwaretechnologie und Robotik | André Dietrich, Sebastian Zug |
| Universitätsbibliothek                    | Oliver Löwe                   |


<h5><p>Prof. Dr. Sebastian Zug, Workshop on e-Learning 2024, Görlitz</p></h5>

---

> Das Vorhaben wird durch den [AK Elearning Sachsen](https://bildungsportal.sachsen.de/portal/parentpage/institutionen/arbeitskreis-e-learning-der-lrk-sachsen/) gefördert. 

<!-- class="reference"-->
> Dieser Vortrag ist eine Open Educational Resource (OER) und steht unter der Lizenz [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.de). Alle enthaltenen Inhalte können frei verwendet werden und sind unter https://github.com/TUBAF-IFI-ConnectedLecturer/Presentations/blob/main/Wel2024/Presentation.md verfügbar

## Kurzvorstellung der Projektpartner

             {{0-2}}
***********************************

__Arbeitsgruppe Softwaretechnologie und Robotik__

***********************************

             {{0-2}}
***********************************

+ _Forschungsfeld 1: Robotik_

   ![](images/Claudi_in_Freiberg.jpg "Forschungsplattform 'Claudi' beim Einsatz in Freiberg")
   ![](images/Schwimmroboter.png "Messdatenaufnahme mit dem Schwimmroboter")

***********************************

             {{1-2}}
***********************************

+ _Forschungsfeld 2: Digitale Lehre_

    Die Arbeitsgruppe entwickelt LiaScript und Edrys als Open Source Lernplattformen für die digitale Lehre.

!?[](https://github.com/TUBAF-IfI-LiaScript/.github/assets/10922356/00a24602-dc63-4b9a-894b-80967b914513 "Darstellung der kollaborativen Entwicklung der Vorlesungsmaterialien mit Studierenden unterschiedlicher Studiengänge")

***********************************

             {{2-3}}
***********************************

__Universitätsbibliothek der Bergakademie Freiberg__

- Lehr- und forschungsunterstützende, informationswissenschaftliche Einrichtung an der TUBAF
- Traditionelle bibliothekarischen Aufgaben (Literaturbeschaffung, -bearbeitung, -distribution) verstärkt in modernen digitalen Bereichen aktiv

  - Open Access Publizieren
  - Forschungsdatenmanagement
  - Open Science
  - Metadatenmanagement / Data Science

- Übernahme von Smart Library Konzepten - Schaffung von Lehr- und Lernräumen (Podcaststudio, AR/VR-Räume)
- Intensive Kooperation mit den Wissenschaftlerinnen vor Ort z.B. Institut für Informatik

<!-- class="reference"-->
> "_Anreicherung digitaler Objekte mit Metadaten in OPAL – Implementierung einer Schnittstelle zur Anbindung externer Recherchesysteme_", 2017/2018, [Link](https://bildungsportal.sachsen.de/impulse/projekt/anreicherung-digitaler-objekte-mit-metadaten-in-opal-implementierung-einer-schnittstelle-zur-anbindung-externer-recherchesysteme/)


***********************************

## Ausgangspunkt OER

> _Open Educational Resources (OER) sind Bildungsmaterialien jeglicher Art und in jedem Medium, die unter einer offenen Lizenz stehen. Eine solche Lizenz ermöglicht den kostenlosen Zugang sowie die kostenlose Nutzung, Bearbeitung und Weiterverbreitung durch Dritte ohne oder mit geringfügigen Einschränkungen._ (Quelle: [UNESCO](https://www.unesco.de/bildung/open-educational-resources))

_Ich veröffentliche meine Lehrmaterialien und freue mich darüber, wenn andere Dozierende/Lernende diese nutzen._

    [(immer )] immer
    [(bisweilen )] bisweilen
    [(gar nicht )] gar nicht

_Ich nutze Materialien anderer Dozierender._

    [(häufig )] immer
    [(bisweilen )] bisweilen
    [(gar nicht )] gar nicht

_Ich habe bereits Inhalte in OPAL mit einer offenen Lizenz hochgeladen._

    [(ja )] ja
    [(nein )] nein

### Motivation

> Warum überhaupt OER?

<div id="example">
<wokwi-led color="red"   pin="13" label="13"></wokwi-led>
<wokwi-led color="green" pin="12" label="12"></wokwi-led>
<wokwi-led color="blue"  pin="11" label="11"></wokwi-led>
<wokwi-led color="blue"  pin="10" label="10"></wokwi-led>
<span id="simulation-time"></span>
</div>

``` cpp Blink.cpp
byte leds[] = {13, 12, 11, 10};

void setup() {
  for (byte i = 0; i < sizeof(leds); i++) {
    pinMode(leds[i], OUTPUT);
  }
}

int i = 0;
void loop() {
  digitalWrite(leds[i], HIGH);
  delay(250);
  digitalWrite(leds[i], LOW);
  i = (i + 1) % sizeof(leds);
}
```
@AVR8js.sketch(example)

{{1-2}}
> OER unterstützen den individuellen Lehrenden bei der Erstellung von interaktiven Lehr-Lern-Inhalten, die die Kapazitäten eines einzelnen übersteigen.

### Herausforderungen bei der Integration von OER

Welche Hemnisse sehen Lehrende bei der Verwendung von OER-Inhalten in Ihrer Lehre?

1. _Rechtliche Unsicherheiten_
2. _Technische Hürden_
3. _Fehlende Passgenauigkeit_
4. _Eigene Qualitätsstandards_
5. ___Aufwändige Suche nach passenden Materialien___
6. ...

<!-- class="reference"-->
> "_Vorstudie zur OER-Initiative sächsischer Hochschulen_" (2023-2024) [Link](https://www.hd-sachsen.de/projekte/oer-initiative-02/2023-07/2024)

<!-- class="reference"-->
> "_Offene Bildungsinfrastrukturen - Anforderungen an eine OER-förderliche IT-Infrastruktur_" (2023), HIS-Institut für Hochschulentwicklung e. V, [Link](https://medien.his-he.de/publikationen/detail/offene-bildungsinfrastrukturen)

<!-- class="reference"-->
> "_Didaktische Metadaten in OER- und Lehrportalen Von der Prämisse pädagogischer Neutralität zur Stärkung einer offenen Lehrpraxis_" (2024), HIS-Institut für Hochschulentwicklung e. V, [Link](https://medien.his-he.de/fileadmin/user_upload/Publikationen/Forum_Hochschulentwicklung/HIS-HE-Forum_Didaktische_Metadaten_in_OER-_und_Lehrportalen.pdf)

### Besondere Motivation mit Blick auf OPAL

Das Projekt der UB zielte 2018 darauf ab die Integration von OER in OPAL zu erleichtern. Entsprechend finden sich die OER-Inhalte als Suchgegenstand in der gewohnten Recherche-Umgebung.

```text @plantUML.png
@startuml
skinparam style strictuml
alt Ist-Zustand
OERAutor_A as "OER\nAutorin" -> OPAL as "OPAL \n ": neues Dokument ohne Metadaten
Lernender_A as "Eingeschriebener\nLenender"--> OPAL : <font color=gray>Zugriff aus dem \n<font color=gray>OPAL Kurs
OPAL --> Lernender_A : <font color=gray>Dokument
OPAL -[#green]> UB_Katalog as "UB \nKatalog": Spiegelung
OERAutor_B as "OER Autor\nLernender" -[#green]> UB_Katalog !!: Suche nach Lern-\nLern-material XY
end

@enduml
```

<iframe src="https://katalog.ub.tu-freiberg.de/Record/finc-172-7PHyQGI" title="Wenig vorbildlicher Datensatz"></iframe><!--style="width:100%; display:block; height: 50vh;"--> 

> Es fehlen die Metadaten für die gezielte Exploration der OER-Inhalte im OPAL!

### Ursachenforschung

![](images/OER_in_OPAL.png "Rot markiert sind die Pflichtfelder - Dateiname und Pfad sowie die Lizenz (hier nicht sichtbar)")

## Projektziele

```text @plantUML.png
@startuml
skinparam style strictuml
alt Projektvision
OERAutor_A -> OPAL : neues Dokument
activate OPAL
OPAL -> OPAL: KI basierte Extraktion
OPAL ->  OERAutor_A: Vorschläge zu den Metadaten
deactivate OPAL
OERAutor_A -> OPAL : ggf. korrigierte Metadaten

OPAL -> UB_Katalog : Spiegelung angereicherter Metadaten
OERAutor_B -> UB_Katalog : Erweiterte Suche
UB_Katalog -> OERAutor_B : 

OPAL -> OERAutor_A : Hinweis auf alternative Materialien\nanderer Autoren

end

@enduml
```

----

Kurzversion der Projektziele:

```ascii
+------------------------------------------------------------+
|    Extraktion von Metadaten                                |        
|    Evaluation mit Autoren                                  |        
|  + Vorschlagssystem                                        |
| ---------------------------                                |
|  = Connected Lecturers                                     |    
+------------------------------------------------------------+                                      .
```


> In diesem Projekt fokussieren wir uns auf die Einzeldateien, die in OPAL hochgeladen werden. Ganze Kurse bleiben außen vor.

## Status der Umsetzung

__Schritt 1: Aggregation der Daten__


```mermaid @mermaid
flowchart LR

    classDef green fill:#5bd21c
    classDef yellow fill:#ffd966
    classDef gray fill:#bcbcbc

    subgraph Datenaggregation
    subgraph OPAL Pipeline  
    direction LR
    OPAL[(OPAL)] --> OPAL_QUERY(OPAL Query):::green
    OPAL_QUERY --> |Ganze  Dateien| OPAL_REPOS[?]
    OPAL_QUERY --> |Einzelne Dateien| TYPE_FILTER[Extrahiere Dateityp]:::green
    TYPE_FILTER -->  |.pdf, .pptx, ... | OPAL_DOWNLOAD[Opal Download]:::green
    TYPE_FILTER -->  |.pdf, .pptx, ... | EXTRACT_OPAL_META[Opal Metadaten]:::green
    OPAL_DOWNLOAD -->  OPAL_FILES[(OPAL Files<br>office,pdf)]
    OPAL_DOWNLOAD -.->  OPAL_METADATA_FILES[(OPAL Meta<br>office,pdf)]
    EXTRACT_OPAL_META -. opal: .->  OPAL_METADATA_FILES[(OPAL Meta<br>office,pdf)]
    end    
    end

    class Datenaggregation, gray
```

<!--
data-type="barchart"
data-title="Datentypen im OPAL-OER Datensatz"
data-show
-->
| Dateityp | Anzahl |
| -------- | -----: |
| `.pdf`   |   6962 |
| `.jpg`   |   1237 |
| `.mkv`   |    869 |
| `.mp4`   |    602 |
| `.png`   |    563 |
| `.zip`   |    466 |
| `.docx`  |    441 |
| `.html`  |    430 |
| `.pptx`  |    224 |
| `.xlsx`  |    208 |
| `.m`     |    182 |
| `.py`    |    171 |
| `.ipynb` |    145 |
| `.mp3`   |    102 |
| `.epub`  |     88 |


> Insgesamt reden wir über 14.015 Dateien! 55% davon gehören zu den Office Datei-Typen (`.pptx`, `.docx`, ...) und `.pdf` Dateien (Stand August 2024).

> Interessanterweise konnten einige Dokumente nicht heruntergeladen bzw. nicht geöffnet werden. Hier waren einige OER schlicht und ergreifend mit einem Passwort geschützt :-)

__Schritt 2: Extraktion der Metadaten__


```mermaid @mermaid
flowchart LR

    classDef green fill:#5bd21c
    classDef yellow fill:#ffd966
    classDef gray fill:#bcbcbc
    classDef white fill:#ffffff,stroke:#ffffff

    subgraph Datenaggregation
    OPAL_FILES[(OPAL Files<br>office,pdf)]
    OPAL_METADATA_FILES[(OPAL Meta<br>office,pdf)]
    end

    class Materialidentifikation, gray

    subgraph Metadatenaggregation
    subgraph OPAL Pipeline
    OPAL_EXTRACTION_TYP_MD(Extraktion Datei-<br> typspezifischer Metadaten):::green
    OPAL_EXTRACTION_LLM_MD(LLM basierte<br>Extraktion Metadaten):::green
    OPAL_EXTRACTION_TYP_MD--> |file:|OPALFILES[(Metadaten<br>Sammlung<br> OPAL)]
    OPAL_EXTRACTION_LLM_MD --> |ai:|OPALFILES
    OPAL_METADATA_FILES --> |opal:|OPALFILES
    end

    subgraph Evaluation
    direction LR
    KREUZVERGLEICH(Kreuzvergleich Autoren):::green 
    KLASSIFIKATION(Normierung der Keywords):::yellow
    PLAUSIBILISIERUNG(Externer Check Autoren)
    BIB_KLASSIFIKATION(Bibliografische Einordung)
    end

    OPALFILES --> Evaluation
 
    end

    OPAL_FILES --> OPAL_EXTRACTION_TYP_MD
    OPAL_FILES --> OPAL_EXTRACTION_LLM_MD


    Evaluation --> METADATA_Analysis(Analyse der Datensätze)
    Evaluation --> METADATA_PROPOSALS(Metadatenvorschläge<br>für Autoren)
    Evaluation --> METADATA_CLASSIFICATION(Materialklassifikation<br>für Autoren)

    class Datenaggregation white
    class Datenaggregation,Metadatenaggregation,Evaluation gray
```

Die Umsetzung der gesamten Pipeline ist unter url als Open Source verfügbar: [Data_aggregation](https://github.com/TUBAF-IFI-ConnectedLecturer/Data_aggregation) verfügbar. Die gesamte Pipeline ist in Python implementiert und nutzt für die AI Komponenten eine Nvidia DGX2. Als LLM kommt aktuell ein [llama3](https://ollama.com/library/llama3) zum Einsatz.

### Herausforderungen

{{0-1}}
<!-- data-type="none" -->
|                          | 495                                                                                                                                     |
| :----------------------- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| `pipe:ID`                | 1PGOlNUd1m7g                                                                                                                            |
| `pipe:file_type`         | pptx                                                                                                                                    |
| `opal:filename`          | cdvost_praesi.pptx                                                                                                                      |
| `opal:oer_permalink`     | https://bildungsportal.sachsen.de/opal/oer/1PGOlNUd1m7g                                                                                 |
| `opal:license`           | CC BY-NC 4.0 Int.                                                                                                                       |
| `opal:creator`           | @red(Oliver Löwe)                                                                                                                       |
| `opal:title`             | Anlagen bergbaulicher Zeichnungen beim Kultur-Hackathon Coding Da Vinci                                                                 |
| `opal:comment`           | Coding Da Vinci Ost von der Universitätsbibliothek Leipzig ausgetragen; 14./15.4.2018; UB Freiberg ist Datengeber der Leupoldsammlungen |
| `opal:language`          | Deutsch                                                                                                                                 |
| `opal:publicationMonth`  | 4                                                                                                                                       |
| `opal:publicationYear`   | 2018                                                                                                                                    |
| `file:author`            | @red(Löwe Oliver)                                                                                                                       |
| `file:keywords`          |                                                                                                                                         |
| `file:subject`           |                                                                                                                                         |
| `file:title`             | Zeichnungen bergbaulicher Anlagen (Leupoldsammlung)                                                                                     |
| `file:created`           | 2018-04-04 10:39:43+00:00                                                                                                               |
| `file:modified`          | 2018-04-14 11:24:44+00:00                                                                                                               |
| `file:language`          |                                                                                                                                         |
| `ai:author`              | @red(Oliver Löwe)                                                                                                                       |
| `ai:affilation`          | TU Bergakademie Freiberg, Universitätsbibliothek                                                                                        |
| `ai:title`               | Es gibt keine Datei mit dem Titel "1PGOlNUd1m7g.pptx" im vorgegebenen Kontext.                                                          |
| `ai:keywords`            | TU Bergakademie Freiberg, Universitätsbibliothek, Leupoldsammlung, Zeichnungen, Montanwesen                                             |
| `ai:keywords2`           | TU Bergakademie Freiberg, Universitätsbibliothek, Leupoldsammlung, Zeichnungen, Bergbau                                                 |
| `ai:dewey`               | 622.8                                                                                                                                   |
| `common_substring_count` | @red(6.0)                                                                                                                               |

                       {{1-2}}
****************************************************

<!-- data-type="none" -->
|                          | 495                                                                                                                                     |
| :----------------------- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| `pipe:ID`                | 1PGOlNUd1m7g                                                                                                                            |
| `pipe:file_type`         | pptx                                                                                                                                    |
| `opal:filename`          | cdvost_praesi.pptx                                                                                                                      |
| `opal:oer_permalink`     | https://bildungsportal.sachsen.de/opal/oer/1PGOlNUd1m7g                                                                                 |
| `opal:license`           | CC BY-NC 4.0 Int.                                                                                                                       |
| `opal:creator`           | Oliver Löwe                                                                                                                             |
| `opal:title`             | Anlagen bergbaulicher Zeichnungen beim Kultur-Hackathon Coding Da Vinci                                                                 |
| `opal:comment`           | Coding Da Vinci Ost von der Universitätsbibliothek Leipzig ausgetragen; 14./15.4.2018; UB Freiberg ist Datengeber der Leupoldsammlungen |
| `opal:language`          | Deutsch                                                                                                                                 |
| `opal:publicationMonth`  | 4                                                                                                                                       |
| `opal:publicationYear`   | 2018                                                                                                                                    |
| `file:author`            | Löwe Oliver                                                                                                                             |
| `file:keywords`          |                                                                                                                                         |
| `file:subject`           |                                                                                                                                         |
| `file:title`             | Zeichnungen bergbaulicher Anlagen (Leupoldsammlung)                                                                                     |
| `file:created`           | 2018-04-04 10:39:43+00:00                                                                                                               |
| `file:modified`          | 2018-04-14 11:24:44+00:00                                                                                                               |
| `file:language`          |                                                                                                                                         |
| `ai:author`              | Oliver Löwe                                                                                                                             |
| `ai:affilation`          | TU Bergakademie Freiberg, Universitätsbibliothek                                                                                        |
| `ai:title`               | Es gibt keine Datei mit dem Titel "1PGOlNUd1m7g.pptx" im vorgegebenen Kontext.                                                          |
| `ai:keywords`            | <!--style="background-color:#FF888888"--> TU Bergakademie Freiberg, Universitätsbibliothek, Leupoldsammlung, Zeichnungen, Montanwesen   |
| `ai:keywords2`           | <!--style="background-color:#FF888888"--> TU Bergakademie Freiberg, Universitätsbibliothek, Leupoldsammlung, Zeichnungen, Bergbau       |
| `ai:dewey`               | <!--style="background-color:#FF888888"--> 622.8                                                                                         |
| `common_substring_count` | 6.0                                                                                                                                     |

> Die DDC Klassifikation 622 trägt das Label "Bergbau und verwandte Tätigkeiten" vgl. [GND](https://lobid.org/gnd/4005614-4)

****************************************************


### Lösungsansätze



<!-- data-type="none" -->
| Problemstellung                                                                                                                                                                   | möglicher Lösungsansatz                                              |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Einige Dateien enthalten urheberrechtliche geschützte Inhalte. Deren Referenzierung muss vermieden werden, bzw. auf korrekte Referenzen im Bibliotheksbestand hingewiesen werden. | Abprüfen der Titel mit dem Bestand der UB.                           |
| Die Fusion der Metadaten aus den unterschiedlichen Quellen (`opal`, `file`, `ai`) ist außerordentlich aufwändig umzusetzen.                                                       | Plausibilitätsprüfung durch die Autorinnen anhand mehrer Vorschläge. |
| Gibt es ggf. Autorinnen und Autoren die (aus welchen Gründen auch immer) eine Einbindung Ablehnen.                                                                                | ?                                                                    |
| Welches Modell kann für die Gruppierung bzw. Ähnlichkeitsanalyse herangezogen werden?                                                                                             | ?                                                                    |

![](images/dewey_decimal_graph.png "DDC Klassifikation für einen Kurs der Autoren im Bereich der Eingebetteten Systeme")


## Danke 

<div class="left">

> Vielen Dank für Ihr Interesse! Wir freuen uns auf Ihre Fragen und Anregungen.

Sebastian Zug

<a href="mailto:sebastian.zug@informatik.tu-freiberg.de">
    sebastian.zug@informatik.tu-freiberg.de 
</a>

------------------

Oliver Löwe

<a href="mailto:oliver.loewe@ub.tu-freiberg.de">
    oliver.loewe@ub.tu-freiberg.de
</a>

</div>

<div class="right">

![](images/URL.png)

</div>


