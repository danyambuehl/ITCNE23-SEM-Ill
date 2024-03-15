---
layout: default
title: Komponenten
nav_order: 3
---

NUR VERLINKEN KEINE BESCHREIBUNG MEHR

## Technologien

Bevor ich die Umsetzung des Projekts beschreibe, gehe ich auf die verwendeten
Technologien, das Konzept und Vorbereitungen ein.

### <img src="../img/bitbucket_logo.png" width="64"> Bitbucket [^1]

Bitbucket ist eine webbasierte Enwicklungsumgebung, die es Entwicklern ermöglicht durch
Repositories gemeinsam an Code-Projekten zu arbeiten.
Die Swisscom besitzt eine eigene Bitbucket GitLab Instanz, welche nur für Swisscom Mitarbeiter zur Verfügung steht.
Auf diesem sollen die Playbooks und Rollen gespeichert werden. Damit verschiedene Personen an den Playbooks arbeiten können, wird ein Repository erstellt, welches von allen Personen bearbeitet werden kann und zentral gespeichert wird.

### <img src="../img/ansible_logo.png" width="64"> Ansible [^2]

Ansible ist ein Open-Source-Tool wodurch sich wiederholende Aufgaben und IT-Prozessen durch sogenannte Playbooks automatisieren lassen.
Nach einem gründlichen Vergleich anhand klar definierter Kriterien wurde für dieses Projekt die Auswahl von Ansible gegenüber Puppet und Chef getroffen.

### <img src="../img/awx_logo.png" width="64"> AWX

AWX ist eine Open-Source-Plattform für Automatisierung und Verwaltung von IT-Aufgaben. 
Es bietet eine webbasierte Benutzeroberfläche, über die Benutzer komplexe Aufgaben, Job-Scheduling, Multi-Playbook-Workflows und vieles mehr orchestrieren können.
Um die Voraussetzung zu erfüllen, dass die Installation entweder manuell über eine Webseite oder gemäß einem festgelegten Zeitplan gestartet werden kann, wird AWX eingesetzt.

### <img src="../img/bpmn_logo.png" width="64"> BPMN 2.0 [^4]

BPMN (Business Process Model and Notation) 2.0 ist eine grafische Notation, die speziell für die Modellierung von Geschäftsprozessen in Unternehmen entwickelt wurde. Es bietet eine standardisierte Möglichkeit, Geschäftsprozesse visuell darzustellen, zu analysieren und zu dokumentieren. 
Und wird hier verwendet um eine detaillierte Dokumentation des "end-to-end" Ablauf der Windows Updates zu erstellen.

### <img src="../img/python_logo.png" width="64"> Python [^5]

Python ist eine meistverwendeten, interpretierte Programmiersprache, die für ihre Vielseitigkeit, Lesbarkeit und umfassende Standardbibliothek bekannt ist.
Lässt sich zudem auf praktisch allen gängigen Betriebssystemen verwenden.
Wird an verschiedenen orten des Projekt verwendet um die Funktionalität zu erweitern. Um z.b PRTG und Veeam Backup and Replication anzusteuern.

### <img src="../img/veeam_logo.png" width="64"> Veeam Backup & Replication [^6]

Veeam Backup & Replication ist eine leistungsstarke Softwarelösung für Datensicherung und Wiederherstellung. Sie bietet umfassende Funktionen zur Sicherung von virtuellen, physischen und cloudbasierten Workload.
Before die Installation der Windows-Updates erfolgen kann wird via selbst geschriebenem Python Script nach aktiven Backup-Jobs geprüft.
Dafür wird das Veeam Backup & Replication API verwendet.

### <img src="../img/prtg_logo.png" width="64"> PRTG Network Monitor [^7]

PRTG Network Monitor ist eine umfassende Netzwerküberwachungssoftware, die es ermöglicht, die Leistung und den Zustand ihres Netzwerks zu überwachen.
Um die Nachvollziehbarkeit und den sauber Ablauf zu gewährleisten, muss das Objekt im Überwachungstool pausiert werden, bevor die Installation der Windows-Updates erfolgt. Wobei das PRTG API v2 verwendet wird.

### <img src="../img/github_pages.png" width="64"> Github Pages [^8]

Github Pages ist ein Hosting-Service, der es Benutzern ermöglicht, statische Websites direkt aus einem GitHub-Repository zu erstellen.
Es wird Jekyll site und eine Github Pipline verwendet um die Dokumentation des Projekts zu veröffentlichen.

### <img src="../img/github_project.png" width="64"> Github Projects [^9]

Github Projects ist ein Tool, das es Benutzern ermöglicht, Aufgaben zu verfolgen, die in einem GitHub-Repository ausgeführt werden.
Wird verwendet um die Aufgaben zu verfolgen und den Fortschritt des Projekts zu dokumentieren.

## Quellen und Referenzen:

[^1]: Bitbucket. (n.d.). [Retrieved from](https://bitbucket.org/)
[^2]: Geerling, J. (2015). Ansible for DevOps. Leanpub. [Retrieved from](https://leanpub.com/ansible-for-devops)
[^3]: AWX. (n.d.). [Retrieved from Link](https://www.ansible.com/products/awx-project)
[^4]: Freund, J und Rücker, B. (2019). Praxishandbuch BPMN Mit Einführung in DMN.[Retrieved from](https://www.hanser-fachbuch.de/fachbuch/artikel/9783446462052)
[^5]:Python Software Foundation. (n.d.). Python. [Retrieved from ](https://www.python.org/)
[^6]:Veeam. (2023). Veeam Backup & Replication. [Retrieved from](https://www.veeam.com/vm-backup-recovery-replication-software.html)
[^7]:Paessler AG. (n.d.). PRTG Network Monitor. [Retrieved from](https://www.paessler.com/prtg)
[^8]:Github. (n.d.). Github Pages. [Retrieved from](https://pages.github.com/)
[^9]:Github. (n.d.). Github Projects. [Retrieved from](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)
