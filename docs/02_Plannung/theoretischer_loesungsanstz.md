---
layout: default
title: Theoretischer Lösungsansatz
parent: Planung
nav_order: 8 
---

## Theoretischer Lösungsansatz

Die in der Planung erarbeiteten Anforderungen und Ziele sollen in diesem Kapitel in einem theoretischen Lösungsansatz zusammengefasst werden.
Dieser Lösungsansatz soll die Grundlage für die spätere Umsetzung bilden.

Im Prinzip soll die Plattform die Möglichkeit bieten, Webseiten einzelner Genossenschaftswohnungen einer Liste hinzuzufügen und zu verwalten.
Auf diesen Webseiten sollte regelmässig nach neuen Wohnungsangeboten gesucht werden.
Sobald ein neuer Eintrag erscheint, sollte eine Benachrichtigung an den Benutzer gesendet werden. Diese Benachrichtigung sollte direkt auf das Smartphone des Benutzers zugestellt werden.

Dieses Projekt soll Open Source sein und für alle zugänglich und erschwinglich sein.

### Architektur

Für das Projekt werden Microservices verwendet, um mehrere Vorteile zu nutzen: erhöhte Flexibilität und Skalierbarkeit, erleichterte Wartung und Weiterentwicklung sowie verbesserte Ausfallsicherheit durch die Isolierung von Diensten. Als Programmiersprache wird Python eingesetzt, da es eine der beliebtesten Programmiersprachen ist und eine Vielzahl von Bibliotheken und Frameworks bietet, die die Entwicklung erleichtern.

### Datenbank

Als Datenbank wird MongoDB oder Datenbank verwendet, da beide Datenbanken eine hohe Leistung und Skalierbarkeit bieten.

### Frontend

Die Benutzeroberfläche ist in HTML geschrieben und sehr einfach gehalten, da es nicht der Schwerpunkt des Projekts ist. Die Benutzeroberfläche wird mit dem Flask-Framework erstellt, da es einfach zu bedienen ist und eine Vielzahl von Erweiterungen bietet, die die Entwicklung erleichtern.

### Benachrichtigungsdienst

Die Benachrichtigungen werden über die Pushover-API gesendet, da sie einfach zu bedienen ist und eine Vielzahl von Funktionen bietet, die die Entwicklung erleichtern.

### DevOps

Die Plattform wird in Docker-Containern bereitgestellt, um die Bereitstellung und Skalierung zu vereinfachen. Die Container werden mit Docker Compose verwaltet, um die Konfiguration zu vereinfachen und die Wartung zu erleichtern.

Die Plattform wird auf einem virtuellen Server gehostet, um die Skalierbarkeit und Ausfallsicherheit zu gewährleisten. Der Server wird von einem Cloud-Anbieter bereitgestellt, um die Wartung und den Betrieb zu vereinfachen.
CI/CD-Pipelines werden verwendet, um die Bereitstellung zu automatisieren und die Qualität zu gewährleisten und die Verwendung durch dritte zu vereinfachen.

Die Plattform wird in einem Git-Repository verwaltet, um die Zusammenarbeit zu erleichtern und die Versionskontrolle zu gewährleisten.

### Monitoring

Als Monitoring-Tool wird flask_monitoringdashboard verwendet, da es einfach zu bedienen ist und eine Vielzahl von Funktionen bietet, die die Überwachung und Wartung erleichtern.

## Service Design

```mermaid
flowchart TB

        direction TB
        %% Define Entwickler Block
        subgraph Entwicklerumgebung["Entwicklerumgebung"]
            Git
            Docker["Docker"]
        end
        %% Define Entwickler Block
        subgraph NOIP["NoIP"]
            semsearch-bau.ddns.net
        end
        
        %% Define AWS Infrastructure Block
        subgraph Infrastructure["AWS Infrastructure (EC2)"]
            direction TB
        %% Define Microservices Block
        subgraph Microservices["Microservices"]
            direction TB
            subgraph sem-search-prod-api
            FlaskFrontend["Flask Frontend"]
            Monitoring["Monitoring"]
            RESTAPI["REST-API"]
            end

            subgraph sem-search-prod-db
            Datenbank["Datenbank"]
            end
            noipagent["NoIP Agent"]

        end
        end
        %% Define GitLab Infrastructure Block
        subgraph GitLab_Infrastructure["GitLab Infrastructure"]
            direction TB
            GitRepository["Git Repository"]
            GitVariables["Git Variables"]
            GitPipeline["Git Pipeline"]
            Registry["Docker Registry"]
        end
        %% Define Pushover Block
        subgraph Pushover
            direction TB
            PushoverService
        end
        %% Define OpenAI Block
        subgraph OpenAi
            direction TB
            ChatGPTAPI
        end
        %% Define Genossenschaften Block
        subgraph Genossenschaften
            Website 
        end

    EndUser["Mobile Phone"]

    %% Define Relationships
    FlaskFrontend <-->|calls| RESTAPI
    Monitoring <--> FlaskFrontend
    Monitoring <--> RESTAPI
    RESTAPI <-->|queries| Datenbank
    GitPipeline -->|builds images| Registry
    GitRepository -->| triggers | GitPipeline
    GitRepository -->| has| GitVariables
    Registry -->|Image gets deployed on | Infrastructure
    RESTAPI -->|sends notifications to| Pushover
    Pushover -->|sends Notification| EndUser
    RESTAPI <-->|queries| OpenAi
    Git <--> |push/pull| GitRepository
    RESTAPI <--> |Web Scraping| Genossenschaften
    GitVariables --> |contains| NOIP
    NOIP --> |Dynamic DNS| noipagent
    FlaskFrontend <--> |calls| EndUser

    %% Define Styles
    style Entwicklerumgebung fill:#FFA07A,stroke:#FF8C00,stroke-width:4px
    style NOIP fill:#FFA07A,stroke:#FF8C00,stroke-width:4px
    style Microservices fill:#FFA07A,stroke:#FF8C00,stroke-width:4px
    style GitLab_Infrastructure fill:#FFA07A,stroke:#FF8C00,stroke-width:4px
    style Infrastructure fill:#FFA07A,stroke:#FF8C00,stroke-width:4px
    style Pushover fill:#FFA07A,stroke:#FF8C00,stroke-width:4px
    style OpenAi fill:#FFA07A,stroke:#FF8C00,stroke-width:4px
    style Genossenschaften fill:#FFA07A,stroke:#FF8C00,stroke-width:4px
```

## Begründung

Der gewählte Lösungsansatz nutzt eine moderne, skalierbare Architektur und bewährte Technologien, um Flexibilität und Effizienz zu maximieren.
Die automatisierte Prozesse in der Entwicklung und Bereitstellung erhöhen die Zuverlässigkeit und Geschwindigkeit des Projekts.
Monitoring-Tools sorgen für eine proaktive Überwachung und Wartung, während Benachrichtigungsdienste die Benutzerfreundlichkeit verbessern.
Die Verwendung von Open-Source-Technologien und Cloud-Hosting ermöglicht eine kostengünstige und zugängliche Lösung für alle Benutzer.
