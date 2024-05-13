---
layout: default
title: Evaluation Datenbank
parent: Planung
nav_order: 1
# Write me a SQL Alchemy Modeles for this Schema -> CHatgpt 
#```python
#uuid.uuid1()    # Unique ID
#```
# docker image ls
# docker image prune
---
## Evaluation Datenbank

Die Wahl der richtigen Datenbank für Ihr Projekt ist von entscheidender Bedeutung.
In diesem Abschnitt werde ich die Vor- und Nachteile von MongoDB und MySQL vergleichen, um die beste Wahl für Ihr Projekt zu treffen werde ich am ende eine Entscheidungsmatrix erstellen

Damit ich einen Überblick über die Datenbanken habe, erstele ich zuerst ein Datenbankschema für beide Datenbanken.

## DB Schema MongoDB

![Schema MongoDB](../img/mongo_db-diagram.svg)

## DB Schema MySQL

![Schema MySQL](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/danyambuehl/ITCNE23-SEM-Ill/main/docs/02_Plannung/sql_schema.iuml)

## Vergleich

Um die Datenbanken zu vergleichen, werde ich die folgenden Kriterien verwenden:

### Performance

Die Performance kann sich je nach Einsatzszenario stark unterscheiden. MongoDB kann bei großen Datenmengen und einfachen Anfragen oft schneller sein. MySQL ist jedoch bei komplexen Anfragen oft performanter, da die relationale Datenstruktur eine effizientere Datenmanipulation ermöglicht.

### Skalierbarkeit

MongoDB wurde für horizontale Skalierbarkeit entwickelt und kann leicht auf mehrere Maschinen verteilt werden. MySQL hingegen ist eher für vertikale Skalierbarkeit optimiert und kann daher bei großen Datenmengen oder hoher Zugriffsrate an seine Grenzen stoßen.

### Datenschema

Ein wesentlicher Unterschied zwischen MongoDB und MySQL ist der Umgang mit Datenschemas. MongoDB verwendet ein flexibles, JSON-ähnliches Format (BSON), das es erlaubt, strukturierte, halb-strukturierte und unstrukturierte Daten zu speichern. MySQL hingegen verwendet ein starres relationales Schema, das die Datenorganisation vorab definiert und Änderungen an der Struktur schwieriger macht.

### ACID-Transaktionen

Obwohl MongoDB in neueren Versionen Transaktionen unterstützt, ist MySQL in der Regel besser geeignet für Anwendungen, die komplexe Transaktionen mit mehreren Operationen erfordern.

### Community und Support

MySQL hat eine lange Geschichte und eine große aktive Community, während MongoDB eine jüngere Technologie mit einer wachsenden Community ist. Beide haben professionellen Support von den jeweiligen Unternehmen.

## Entscheidungsmatrix

| **Datenbank**  (1-5)  | **Performance**    | **Skalierbarkeit**  | **Flexibilität des Datenschemas** | **ACID-Transaktionen**  | **Community und Support**      | **Gesamtpunktzahl**  |
|---------------------  |------------------  |---------------------|---------------                    | --------------          | -----------------------------  | -------------------- |
| Gewichtung            | 0.3                | 0.1                 | 0.1                               | 0.3                     |   0.3                          |                      |
| MongoDB               | 3                  | 4                   | 4                                 | 3                       |   3                            | 3.5                  |
| MySQL                 | 4                  | 2                   | 2                                 | 5                       |   4                            | 4.3                  |

## Fazit

Beide Datenbanken haben ihre Vor- und Nachteile und eignen sich für unterschiedliche Anwendungsfälle.
Anhand der Entscheidungsmatrix lässt sich jedoch feststellen, dass MySQL insgesamt besser abschneidet und daher die bessere Wahl für dieses Projekt ist.
