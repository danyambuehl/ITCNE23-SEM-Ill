---
layout: default
title: Organisation
parent: Projekt
nav_order: 1
---

## Inhaltsverzeichnis
{: .no_toc .text-delta }

1. TOC
{:toc}

## Projektaufbauorganisation

Die folgende Grafik stellt den Aufbau meines Projektes dar.

![Projektorganisation](../img/projectorganisation.png)


## Git Hub Projekt Management

### Kanban Board


Für dei Projektorganisation verwenden ich das Github Projekt Management Tool.
Um den Workflow in diesem agilen Projekt zu visualisieren und zu verwalten, verwenden ich das Kanban-Board direkt in Github als mein Projektmanagement-Tool. 
Ziel ist es, eine klare und visuelle Darstellung des gesamten Workflows zu haben, die es uns ermöglicht, den Status aller Aufgaben leicht zu sehen.

Ich habe mich für ein schlankes und einfaches Kanban-Board-Design entschieden, bei dem die folgenden Spalten die verschiedenen Stufen/Prozesse des Projekts darstellen.

| **Todo**                                      | **Backlog**                                           | **in Progress**      | **Done**      |
|-----------------------------------------------|-------------------------------------------------------|----------------------|---------------|
| Offene Task, welche im aktuellen Sprint sind. | Diese Tickets befinden sich nicht im aktuellen Sprint | Task in Bearbeitung. | Task erledigt |

![Kanban Board](../img/kanbanboard.png)

### Task Definitionen


Jedes Ticket hat folgende Werte gesetzt und definiert.

| **Titel**                                | **Beschreibung**                                              |
|------------------------------------------|---------------------------------------------------------------|
| Assignees                                | Person, welche den Task umsetzt.                              |
| Status                                   | Status - Todo, In Progress, Done                              |
| Milestone                                | Verlinkung mit dem Sprint in welchen die Arbeit gemacht wird. |
| Linked pull requests / Repository Branch | Verlinkung mit GIT-Branches                                   |
| Start Date                               | Start der Arbeiten                                            |
| End Date                                 | Ende der Arbeiten                                             |
| Priority                                 | Priorität der Arbeit - Low, Normal, High                      |

## Veröffentlichung der Arbeit

Das Projekt wird in Markdown geschrieben und mithilfe von Jekyll in eine vollständig statische Webseite umgewandelt.
Mithilfe von Github Actions wird eine Pipeline verwendet die den Prozess des veröffentlichen der Webseite vollumfänglich automatisiert, sobald Änderungen im Repository vorgenommen werden.
Die Webseite wird auf Github Pages veröffentlicht und kann unter folgendem Link aufgerufen werden.

> https://danyambuehl.github.io/ITCNE23-SEM-Il/

Durch diese Vorgehensweise wird eine effiziente und gut gestaltetet Projektdokumentation gewährleistet und die Arbeit kann einfach und schnell veröffentlicht werden.
