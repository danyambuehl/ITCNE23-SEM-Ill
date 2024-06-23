---
layout: default
title: Herausforderungen
parent: Abschluss
nav_order: 3
---

## Was waren die Herausforderungen?

Hier nochmal die Herausforderungen, die ich gemeistert haben:

### Herausforderung 1: Mermaid Diagramme erstellen

Mich in Mermaid einzugewöhnen und die Diagramme zu erstellen war eine Herausforderung.
Ich habe mich sehr schnell in das erstellen von Diagrammen eingearbeitet und darauf geachtet das ich mehrere verschiedene Diagramme erstelle.
Das erstellen von Diagrammen hat mir sehr viel Spass gemacht und ich habe sehr viel dabei gelernt.
Jedoch ist es auch sehr zeitaufwändig und ich hatte anfangs Schwierigkeiten die Diagramme auch in Jekyll zu integrieren.

### Herausforderung 2: Dokumentation

Die Dokumentation war sehr umfangreich und ich musste sehr viele Dokumente erstellen.
Das Projektmanagement wurde letztes Semester sehr stark gewichtet und ich habe mich entschieden, dieses Semester auch sehr viel Wert auf das Projektmanagement zu legen.
Einen grossen mehrwert sehe ich darin nur teilweise, da ich sehr viel Zeit in die Dokumentation investiert habe und dadurch weniger Zeit für die Umsetzung hatte.
Zusätzlich fehlt mir das Feedback von dem Dozenten, da ich kein konstruktives Feedback zu den einzelnen Dokumenten erhalten habe.

### Herausforderung 3: Scrapping

Ich habe mir das Scrapping sehr einfach vorgestellt, jedoch war es sehr aufwändig und ich habe sehr viel Zeit in die Umsetzung investiert.
Das Hauptproblem war, dass sich jede Website anders verhält und sehr regelmässig geändert werden. Dadurch musste ich sehr viel Zeit in die Fehlerbehebung investieren.
Zuerst habe ich versucht, mit BeautifulSoup die html content Daten zu bereinigen (process_html, function), jedoch war dies sehr aufwändig und musste für jede Website individuell angepasst werden.
Nach einer Idee des Fachexperten habe ich mich entschieden, die unstrukturierten Daten mit ChatGPT zu analysieren und zu strukturieren.

### Herausforderung 4: ChatGPT

Schnell habe ich gemerkt, dass die ChatGPT-API durchaus zügig kosten generiert.
Daher habe ich mich entschieden, eine art selbstlernende Funktion zu implementieren, die das HTML-Element analysiert und die Daten in der Datenbank speichert.
Das nächste mal wenn auf dieser Website nach einem Apartment gesucht wird, kann die Funktion auf die Daten in der Datenbank zurückgreifen und muss nicht erneut die ChatGPT-API anfragen.
Um jedoch eine konstante Antwort zu erhalten, musste ich sehr viel Zeit in die Fehlerbehebung investieren und die Funktionen mehrmals neu schreiben.

### Herausforderung 5: Beautiful Soup mit lxml

Die Verwendung von lxml war eine Herausforderung, da für die Verwendung von 'lxml' System Packages benötigt werden, die nicht im requirements.txt installiert werden können.
Dies hat mich sehr viel Zeit gekostet, jedoch habe ich mich hierfür tiefer in die Dockerfiles eingearbeitet und konnte so sehr viel lernen.