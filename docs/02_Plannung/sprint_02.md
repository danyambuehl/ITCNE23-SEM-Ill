---
layout: default
title: Sprint 02
parent: Planung
nav_order: 11
---

## Sprint 02

| Datum                  | Aktivität                                            | Dauer      |
|-----------------------|------------------------------------------------------|------------|
| 10.05.24 - 27.05.24   | Sprint 01                                            | 18 Tage    |
| 27.05.24              | Einzelbesprechung Zwischenstand                      | 1 Tag      |
| 28.05.24 - 14.06.24   | Sprint 02                                            | 18 Tage    |
| 15.06.24 - 04.07.24   | Sprint 03                                            | 20 Tage    |
| 05.07.24 - 08.07.24   | Abgabe der Arbeit / Schlusspräsentationen (online)   | 4 Tage     |

```mermaid
gantt
    title Projektplan ITCNE23-SEM-lll
    dateFormat  DD.MM.YY
    axisFormat  %d.%m.%Y

    %% Define the sections
    section Zwischenbesprechung
    Einzelbesprechung Zwischenstand           : milestone,   meet,         27.05.24, 1d

    %% Define the Sprints
    section Sprints
    Sprint 01                                   : active, sprint,  10.05.24, 18d
    Sprint 02                                   : sprint,  28.05.24, 18d
    Sprint 03                                   : sprint,  15.06.24, 20d
    Abgabe der Arbeit / Schlusspräsentationen (online) : active, present,  05.07.24, 4d

```

### Sprint Planning

Folgende Tasks wurden im Sprint 02 geplant:

![Sprint Planning](../img/sprint_02.png)

### Sprint Review

Folgende Tasks wurden im Sprint 02 bearbeitet:

![Sprint Planning](../img/sprint_02_ende.png)

### Sprint Retrospektive

#### Funktionen implementiert

In diesem Sprint habe ich mich auf die Implementierung der Überwachungsfunktion konzentriert. Ich habe die Funktionen `find_div_static` und `find_div_dynamic` implementiert. Die Funktion `find_div_static` sucht nach einem statischen HTML-Element auf der Website des Unternehmens. Die Funktion `find_div_dynamic` sucht nach einem dynamischen HTML-Element.

Die grosse Herausforderung war das implementieren der chatgpt-api. Ich habe die Funktion `ask_chatgpt_about_apartment` implementiert. Diese Funktion fragt die ChatGPT-API ob auf der Website des Unternehmens ein Apartment aufgelistet ist. Die ChatGPT-API antwortet spezifisch mit `Yes` wenn ein Apartment im html context ersichtlich ist.

Jedoch speziell die Implementierung der Funktion `ask_chatgpt_about_html_class` bin ich sehr stolz. Diese Funktion fragt die ChatGPT-API nach dem HTML-Klassenname des zuvor gefundenen Apartments auf der Website. Die ChatGPT-API antwortet mit dem HTML-Klassenname und ich speichere diesen in der Tabelle des Unternehmens ab wo die Funktion `find_div_dynamic` darauf wieder auf den Wert zugreifen kann.

Des Weiteren habe ich die Funktion `send_message_to_me` implementiert. Diese Funktion sendet eine Benachrichtigung an den Benutzer, wenn sich der Inhalt der Website des Unternehmens geändert hat.

Schlussendlich habe ich die Funktion `update_company_record` implementiert. Diese Funktion aktualisiert den Datensatz des Unternehmens in der Datenbank des Unternehmens.

#### Dockerfile

Das requirements.txt file war auch eine Herausforderung.
Damit das Scrapping funktioniert, musste ich die Bibliothek `playwright` installieren. Dies war nicht einfach, da ich auch die richtige Version von playwright finden musste, die mit der Version von Python und den anderen Bibliotheken kompatibel ist.

Die Bibliothek für `grenlet` war auch eine Herausforderung und ich musste schlussendlich auf Python 3.11.0 wechseln, damit die Bibliothek funktioniert.

#### Fazit

Es gab viel Ausprobieren und Fehlerbehebung in diesem Sprint. Ich musste Funktionen mehrmals neu schreiben, um sie zum Laufen zu bringen. Es wurden auch mehr Bibliotheken installiert, als ich geplant hatte. Im nächsten Sprint werde ich versuchen, es einfacher zu halten und von begin weg die Funktionen mehr zu testen.

**Keep** Was soll beibehalten werden?

- Probieren und Fehler machen
- Funktionen in kleine Teile aufteilen

**Drop** Mit was soll ich aufhören?

- Funktionen ständig umschreiben
- Weitere Bibliotheken installieren

**Try** Was soll ich im nächsten Sprint ausprobieren?

- Simplicity
- Mehr testen der Funktionen
