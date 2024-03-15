---
layout: default             #layout: minimal
title: Smart Ziele
nav_order: 4
---

## SMART-Ziele

| **Spezifisch**               | **Messbar**              | **Erreichbar**      | **Relevant**              | **Zeitgebunden**      |
|------------------------------|--------------------------|---------------------|---------------            | --------------        |
| Klar definierte und präzise  | Quantifizierbare Aspekte | Realistische  Ziele | Bedeutung für das Projekt | klaren Zeitrahmens    |

**Automatisierung der Windows-Updates:**

Bis zum Ende des dieses Jahres entwickeln und implementieren ich eine Automatisierungslösung für den gesamten Prozess der Windows-Update-Aufgaben, einschließlich Monitoring, Installation der Updates und Neustart der Systeme. 
Diese Lösung wird alle Windows-Update-Aufgaben für alle 16 Server in der Testumgebung fehlerfrei durchführen, unter Berücksichtigung der verfügbaren Ressourcen und des zeitlichen Rahmens.
Die Automatisierungslösung trägt dazu bei, die Effizienz zu steigern, menschliche Fehler zu minimieren und die Sicherheit der Systeme zu gewährleisten.

**BPM-Dokumentation des Automatisierungsablaufs:**

Vor dem Ende des dritten Sprints wende ich BPM-Methoden an, um eine detaillierte Dokumentation des automatisierten Ablaufs der Windows-Update-Aufgaben zu erstellen. Diese BPM-Dokumentation wird eine klare Darstellung aller Schritte, Entscheidungen und Ausnahmen bieten, unter Berücksichtigung der Komplexität des Ablaufs. Die detaillierte BPM-Dokumentation fördert das Verständnis und schafft Transparenz im Ablauf.

**Integration von Python zur Veeam Backup & Replication Überwachung:**

Bis zum Ende des zweiten Sprints entwickele ich ein Python-Skript zur Integration von Ansible mit der Veeam Backup & Replication über REST API. Das Skript wird die Backup-Infrastruktur nach laufende Backup-Jobs abfragen. 
Die Entwicklung erfolgt unter Berücksichtigung der verfügbaren Veeam-API-Dokumentation und der REST API Möglichkeiten. Die Integration von Python zur Veeam Backup & Replication Überwachung trägt dazu bei, den Status der Backup-Infrastruktur festzuhalten und zu gewährleisten eines sauberen automatisierten Neustarts der Betroffenen Servern.

**Integration von PRTG-Monitoring und Windows Services**

Überwachungsobjekte in PRTG pausieren und nach dem Update wieder fortzusetzen sowie Vergleichen der Windows Dienste vor und nach dem Neustart.
Um PRTG anzusprechen wird das neu entwickelte PRTG API v2 verwendet. 

Bis zum Ende des Projekt integriere ich das PRTG-Monitoring System, indem ich die Überwachungsobjekte in PRTG vor dem Update automatisch pausieren und danach wieder fortsetze. Gleichzeitig vergleichen ich die Windows-Dienste vor und nach einem Neustart mithilfe eines Ansible Playbooks. Die Funktionalität wird durch erfolgreiche Anwendung der PRTG API v2 gemessen. Die Integration erfolgt unter Berücksichtigung der verfügbaren Technologien. Durch die optimierte Überwachung und den präzisen Vergleich vor und nach einem Neustart trägt die Integration dazu bei, Systemstabilität und Konsistenz sicherzustellen.