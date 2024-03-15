---
layout: default
title: Einleitung 
nav_order: 1
permalink: /
banner: /img/banner_2.png
---
![Custom Banner](/docs/img/logo.png)

## Zusammenfassung 

| Projektname | ITCNE23-SEM-II |
|---|---|
| Titel der Semesterarbeit | Automatisierung der Windows Updates  |
| Projekt Experte | Rohr Philipp |
| IaC Experte | Armin Dörzbach |
| Student | Dany Ambühl  |
| Problemstellung | Automatisierung meiner monatlich wiederkehrenden Windows-Update-Aufgaben |
| Ziele  | - Automatisierung der Windows-Updates |
|   | - BPM-Dokumentation des Automatisierungsablaufs: |
|   | - Integration von Python zur Veeam Backup & Replication Überwachung: |
|   | - Integration von PRTG-Monitoring und Windows Services  |
|   | - Pipeline zum Erstellen und Veröffentlichen der Arbeit |
| Meilensteine | 1.Sprint - Projekt-Kickoff beendet, einzelne Aufgaben begonnen |
|  | 2.Sprint - Implementierung der Automatisierungslösung |
|  | 3.Sprint - Prio A-Aufgaben abschliessen und Überarbeitung der Dokumentation, Schlusswort |

## Projektbeschreibung

Die Aktualisierung von Windows-Systemen ist entscheidend, um Sicherheit und Stabilität zu gewährleisten. Manuelle Verwaltung und Installation von Updates auf mehreren Systemen können jedoch sehr zeitaufwendig und fehleranfällig sein.
Glücklicherweise kann mein Team mit der Hilfe von Automatisierungstools den Prozess optimieren und sicherstellen, dass unsere Systeme stets auf dem neuesten Stand sind.

Unser Team möchten den manuellen Aufwand bei der Bereitstellung von Windows-Updates vermindern. Dabei soll die Automatisierungslösung auf die bestehende Infrastruktur aufbauen und die bestehenden Prozesse berücksichtigen. Die Lösung soll die Installation von Windows-Updates auf allen Systemen vereinfachen, die Konsistenz sicherstellen, Effizienz steigern und die fehleranfälligkeit reduzieren.
Es soll eine Infrastruktur eingerichtet werden, um auch zukünftig weitere Aufgaben zu automatisieren.

### Aufgabenstellung and die Automatisierung der Windows Updates

Die Installation der Windows-Updates auf allen Systemen, sollte manuell über eine Webseite oder nach einem festgelegten Zeitplan gestartet werden können.
Die Authentifizierung sollte möglichst über Active Directory erfolgen und verschlüsselt sein.
Vor der Installation müssen einige "Pre-Checks" durchgeführt werden, um zu gewährleisten, dass die jeweiligen Systeme bereit sind.

Dazu gehören:

- die Überprüfung des verfügbaren Speicherplatzes auf dem C: Laufwerk
- die Registrierung laufender Dienste
- die Überprüfung des Status der Veeam Backup-Jobs
- das Pausieren des Objekt im Überwachungstool.

Nach erfolgreicher Installation und dem obligatorischen Neustart wird zusätzlich erneut nach zu installierenden Windows-Updates überprüft und bei Bedarf installiert. Des Weiteren werden die folgende "Post-Checks" durchgeführt:

- Aktuell laufenden Dienste mit denen vor dem Neustart verglichen.
- Der Überwachungsstatus wird wieder aktiviert.
- Um die Nachvollziehbarkeit zu gewährleisten, ist eine minimale Protokollierung erforderlich.



## Sachmittel

**Folgende Technologien werden für die Umsetzung des Projekts benötigt:**

- Swisscom GIT
- PRTG API v2
- Veeam Backup and Replication REST API
- Camunda 
- Python 
- Automatisierungslösung
- GUI 
- GitHub Pages

**Vorgaben, Methoden und Werkzeuge:**

- Lean Methode
- Kanban
- Roadmap
- SMART
- SEUSAG
- BPM Geschäftsprozesse
  
**Werkzeuge:**

- Visual Studio Code
- Draw.io
- GitHub 
- PyCharm
- Camunda Modular

## Risiken

**Stärken:**

- Automatisierung der monatlichen Windows-Update-Aufgaben ermöglicht Effizienzsteigerung, deutlich verbesserten Zuverlässigkeit und Konsistenz.
- Die Kombination aus Automatisierung der Windows-Updates, Monitoring, BPM-Dokumentation und Integration mit Veeam Backup schafft eine umfassende Lösung.
- Automatisierte Windows-Updates tragen zur Sicherheitsverbesserung und Einhaltung von Compliance-Richtlinien bei.
- Die Einbeziehung verschiedenen Themenbereichen wird das Verständnis für die unterschiedlichen Technologien verbessern."


**Schwächen:**

- Implementierung einer umfassenden Automatisierungslösung erfordert gründliche Planung und Umsetzung, da sehr viele Schnittstellen bestehen und dies zu Komplexität führen kann.
- Die Integration mit Veeam Backup & Replication und PRTG erfordert Abhängigkeit von Drittanbietern, was potenziell zusätzliche Komplexität und Unsicherheit mit sich bringen könnte.


**Chancen:**

- Die Automatisierungslösung bietet die Möglichkeit Anpassung an zukünftige Anforderungen, einschließlich Erweiterungen auf andere Systeme und Prozesse.
- Durch Überwachung mit PRTG und Integration mit Veeam Backup & Replication, können verbesserte Abläufe implementiert werden.


**Bedrohungen:**

- Schnelle Veränderungen in Technologien und Standards können die Langzeit-Integration beeinträchtigen.
- Die Automatisierung und Integration von kritischen Systemen bergen Sicherheitsrisiken, die sorgfältige Sicherheitsmaßnahmen erfordern.

## Strategien

Um die Schwächen der SWOT-Analyse zu adressieren.

- Sensibilisiere das Team für Sicherheitsrisiken
- Anwendung des Prinzips der geringsten Berechtigung, wo immer möglich.
- Entwickle eine detaillierte Planung, Ablauf und Systemarchitektur, um die Komplexität zu minimieren und Verständnis zu Stärken.
- Ich entwerfe mein Projekt mit dem Gedanken an zukünftige Entwicklungen und Trends, um sicherzustellen, dass es skalierbar und anpassbar ist.
- Erstellen von Log eintragen zur Nach Vollziehbarkeit.
- Allenfalls Manuelle Tasks einplanen, um die Komplexität zu reduzieren.


## Prioritäten

**Erforderlich:**

- Automatisierung der Windows-Updates.
- BPM-Dokumentation des Automatisierungsablaufs.
- Integration von Python zur Veeam Backup & Replication Pré-Update-Überwachung.
- Integration von PRTG Monitoring Tool
- Vergleichen der Windows Dienste vor und nach dem Neustart.

**Optional:**

- Integration von Python zur Veeam Backup & Replication Post-Update-Überwachung.
- Anbinden von Servern ausserhalb der Domain 


## Notizen

**Immer auf Model oder Theory verweisen**

- Vorrecherche auf Machbarkeit erstellen
- Zwischenziele setzen.
- Self Healling