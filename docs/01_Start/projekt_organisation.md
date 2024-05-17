---
layout: default
title: Projektorganisation
parent: Start
nav_order: 3
---

## Projektaufbauorganisation

Diese Seite beschreibt die Organisation meines Projekts und die Struktur meines Scrum-Teams.
Die folgende Grafik stellt den Aufbau meines Projektes dar.

![Projektorganisation](../img/project_organisation.png)

## Team Strucktur

Und hier ist die Struktur meines Scrum-Teams, in der die Rollen der einzelnen Personen sowie ihre Beziehungen zueinander dargestellt werden.

```mermaid
C4Context

%% Define persons
Person(Philipp, "Rohr Philipp", "Expert")
Person(Marcel, "Marcel", "Expert")
Person(Boris, "Langer Boris", "Expert")
Person(End, "End User")

%% Define boundary with Dany's roles
Enterprise_Boundary(b1, "Scrum Team") {
  Person(Dany, "Dany", "Product Owner / Scrum Master / Entwickler")

}

Boundary(b2, "Insitution") {
  Person(tbz, "TBZ")
}

Boundary(b3, "End User") {
  Person(End, "Wohnungssuchende")
}

%% Define relationships
Rel(Philipp, Dany, "Reviews, and feedback")
Rel(Boris, Dany, "Consulting, reviews, and feedback")
Rel(Marcel, Philipp, "Reviews")
Rel(Marcel, Boris, "Reviews")
Rel(Dany, End, "Feedback ")
Rel(End, Dany, "Feedback ")
Rel(tbz, Dany, "foster")


```

## Scrum Team Rollen

### Product Owner

Der Product Owner ist verantwortlich für die Maximierung des Wertes des Produkts und die Arbeit des Entwicklungsteams. Er ist der Hauptverantwortliche für die Entwicklung und Umsetzung des Projekts.

### Scrum Master

Der Scrum Master ist verantwortlich für die Einhaltung der Scrum-Regeln und -Praktiken. Er unterstützt das Team bei der Umsetzung der agilen Methoden und sorgt für eine effiziente arbeiten.

### Expert

Die Experten sind verantwortlich für die Unterstützung und Bewertung des Projekts. Sie geben Feedback und beraten das Team bei der Umsetzung.

### End User

Die Endbenutzer sind die potenziellen Nutzer der entwickelten Plattform zur Wohnungssuche. Sie geben Feedback und Anregungen zur Verbesserung des Produkts.
