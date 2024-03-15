---
layout: default             #layout: minimal
title: Sprints
nav_order: 4
---

## Abschluss der Sprints

Hier werden die einzelnen Sprints dokumentiert und die Erfahrungen festgehalten.
Dabei wird das retrospektive Technik mit dem **"Keep, Drop, Try"** Prinzip angewendet
Um die einzelnen Sprint-Abschlüsse zu evaluieren und Verbesserungen für zukünftige Sprints zu identifizieren.

## Kanban Board Sprint 1

Der Beginn der Semesterarbeit verlief reibungslos. Es wurden umfangreiche Aufgaben zur Informationsbeschaffung, Recherche aller Optionen und zur Projektplanung erledigt, die leider viel Zeit in Anspruch genommen haben. Trotz des zeitlichen Aufwands waren diese Schritte für solch ein komplexes Projekt unabdingbar.

| **Sprint Ziel**                                         | **Status** |
| ------------------------------------------------------- | ---------- |
|  **Start Datum**                                         | **06.11.2023**   |
|  **End Datum**                                           | **27.11.2023**   |
| Projektstart                                            | 100%       |
| Erstellen der Grundstruktur des Repository              | 100%       |
| Github Project erstellen mit Meilensteinen              | 100%       |
| Dokumentation Projektmanagement erstellen               | 95%        |
| Tickets erstellen für die Projektarbeit                 | 100%       |
| Einrichten von GitHub Actions / Projects / Pages        | 100%       |
| Infrastruktur aufsetzen                                 | 100%       |
| Dokumentation Infrastruktur erstellen                   | 100%       |

![1.Sprint](../img/sprint_1_list.png)

**Keep / Beibehalten**

- Motivation beibehalten
- Laufend Issues erstellen

**Drop / Stopp**

- Keines

**Try / Ausprobieren**

- Mehr Dokumentation erstellen
- Mehr Notizen machen zu den einzelnen Problemen

# Pro Thema
##AWS Certified Cloud Practitioner 
Die Zertifizierung zum AWS Certified Cloud Practitioner hat mehr Zeit in Anspruch genommen als geplant. Nachdem der erste Zertifizerungsversuche gescheiter war, habe ich mich mit folgenden Udemy Kursen auf die Prüfung vorbereitet Ultimate AWS Certified Cloud Practitioner CLF-C02 / 6 Practice Exams | AWS Certified Cloud Practitioner CLF-C02. Bei den Übungen hatte ich dann bemerkt, dass ich vielfach bei den selben Themen immer wieder Probleme hatte. Somit habe mir mittels Anki eine quelloffene Lernkartei-Software installerit und diese Punkte so zusätliche gelernt. Am 05.12.2023 konnte ich dann die Zertifizierung erfolgreich abschliessen. AWS Certified Cloud Practitioner certificate

## IaC

Nachdem ich mich in das AWS SDK eingearbeitet hatte, entschied ich mich dazu, sämtliche Automatisierungen mit Hilfe von boto3 (Python) durchzuführen. Daher habe ich die bestehenden AWS CLI Bash-Scripts aus dem Sprint 1 direkt umgeschrieben.

Die Automatisierung mittels Boto3 gestaltete sich jedoch aufwändiger als erwartet, insbesondere aufgrund der komplexen Abhängigkeiten zwischen Lambda-Funktionen, Rollen, Richtlinien und CodeBuild. Besonders herausfordernd war die Implementierung der CodeBuild-Automatisierung. Die Dokumentation allein lieferte nicht ausreichend Klarheit darüber, welche Werte zwingend erforderlich sind und wie sie korrekt eingefügt werden müssen. In diesem Zusammenhang war es hilfreich, die Erstellung über die grafische Benutzeroberfläche durchzuführen und die Konfiguration anschliessend in eine JSON-Datei zu exportieren.

Dieser Sprint war äusserst lehrreich im Kontext des Deployments mithilfe von CodeBuild und GitHub. In CodeBuild wird die Source (GitHub), das Container-Image für die Verarbeitung sowie die zu berücksichtigenden Ereignisse (Webhook) festgelegt. Eine interessante Option besteht darin, dass neben dem Ereignis (Push) auch Abhängigkeiten zur Commit-Nachricht definiert werden können. Auf diese Weise können für das Deployment spezifische Abhängigkeiten zwischen dem Ereignis und der Nachricht festgelegt werden. Zusätzlich müssen die entsprechenden Berechtigungen (Policy/Role) vorhanden sein.

Aus den Erkenntnissen aus diesem Sprint, würde ich heute den IaC Teil direkt mit boto3 umsetzten. Des Weiteren war die Zwei-Faktor-Authentifizierung über Microsoft Authenticator für AWS und GitHub eher lästig. Daher habe ich mich entschieden, zwei YubiKeys (yubikey-5c-nano / yubikey-5c-nfc) anzuschaffen. Nach der Registrierung gestaltet sich die Anmeldung äusserst entspannt. Diese Schlüssel können zudem für verschiedene Online-Anwendungen genutzt werden.

## FaaC 
In diesem Sprint wurde mir klar, dass ich zusätzliche AWS-Komponenten benötige (API Gateway), damit die Function via Web erreichbar ist. Dies bedeutet, dass im Sprint 3 weiterhin Zeit für die Infrastruktur als Code (IaC)-Umsetzung investiert werden muss, und mir daher die Zeit für die Entwicklung von Functions as a Service (FaaS) fehlt. Es würde ein zusätlichner Issue für den Sprint 3 erfasst AWS API Gateway.

Trotz dieser Herausforderung habe ich mich dazu entschieden, den Fokus auf die IaC zu legen und den FaaS-Teil so einfach wie möglich zu halten.