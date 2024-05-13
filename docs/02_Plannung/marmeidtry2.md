---
layout: default
title: MERMEID TRY 2
parent: Planung
nav_order: 1
# Write me a SQL Alchemy Modeles for this Schema -> CHatgpt 
#```python
#uuid.uuid1()    # Unique ID
#```
# docker image ls
# docker image prune
---

Here is a simple flow chart:

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

```mermaid
---
title: Animal example
---
classDiagram
    note "From Duck till Zebra"
    Animal <|-- Duck
    note for Duck "can fly\ncan swim\ncan dive\ncan help in debugging"
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
        +String beakColor
        +swim()
        +quack()
    }
    class Fish{
        -int sizeInFeet
        -canEat()
    }
    class Zebra{
        +bool is_wild
        +run()
    }
```

```mermaid
erDiagram
    Companies ||--o{ Apartments : "references"
    Companies ||--o{ Contact : "contains"
    Apartments ||--o{ Details : "contains"
    Apartments ||--o{ HistoricStatus : "has many"
    Users ||--o{ Preferences : "has"

    Companies {
        string _id PK "MongoDB ObjectId"
        string name "Name des Unternehmens"
        string website "Webseite des Unternehmens"
        date last_scraped_at "Datum und Uhrzeit, wann die Webseite zuletzt gescraped wurde"
        string status "Status der Webseite, z.B. 'aktiv', 'inaktiv' etc."
    }

    Contact {
        string phone "Telefonnummer (falls vorhanden)"
        string email "E-Mail Adresse (falls vorhanden)"
        string address "Büroadresse (falls vorhanden)"
    }

    Apartments {
        string _id PK "MongoDB ObjectId"
        string company FK "Referenz auf das Immobilienunternehmen"
        string url "URL der Webseite, von der die Wohnung gescraped wurde"
        string hash "Hash des HTML-Inhalts"
        date scraped_at "Datum und Uhrzeit, wann die Wohnung gescraped wurde"
        string status "Status der Wohnung, z.B. 'frei', 'vermietet' etc."
    }

    Details {
        string address "Adresse der Wohnung"
        int rooms "Anzahl der Zimmer"
        date availableFrom "Verfügbar ab (falls vorhanden)"
        float price "Preis der Wohnung (falls vorhanden)"
        float size "Größe der Wohnung in Quadratmetern (falls vorhanden)"
        int floor "Stockwerk (falls vorhanden)"
        string otherDetails "Andere Information über die Wohnung (falls vorhanden)"
    }

    HistoricStatus {
        string status "Status"
        date from "from Date"
        date to "to Date"
    }

    Users {
        string _id PK "MongoDB ObjectId"
        string username "Benutzername"
        string password "Passworthash"
        string email "E-Mail-Adresse des Benutzers"
        date signedUpAt "Datum und Uhrzeit, wann der Benutzer sich angemeldet hat"
    }

    Preferences {
        float priceRange_min "min Preisbereich"
        float priceRange_max "max Preisbereich"
        int roomRange_min "min Zimmeranzahl"
        int roomRange_max "max Zimmeranzahl"
    }

```