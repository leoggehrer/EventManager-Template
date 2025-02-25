# EventManager – Ein Veranstaltungsverwaltungssystem

**Lernziele:**

- Entwicklung eines datenzentrierten Software-Systems mit klarer Architektur.
- Implementierung einer Konsolenanwendung zur Verwaltung von Veranstaltungen, Teilnehmern und Locations.
- Nutzung von Datenbanken für die Speicherung und Abfrage von Daten.
- Anwendung von Schnittstellen und Geschäftslogik.

---

## Projektstruktur

Das Projekt **'EventManager'** dient als Beispiel für die Entwicklung eines Event-Management-Systems. Es besteht aus mehreren Komponenten, die eine vollständige Anwendung ergeben.

| Name | Beschreibung | Typ |
|------|------------- |-----|
| **EventManager.Common**        | In diesem Projekt werden alle Klassen gesammelt, die in anderen Projekten verwendet werden (Schnittstellen, Hilfsfunktionen usw.). | Bibliothek |
| EventManager.Common.Contracts  | In diesem Abschnitt befinden sich alle Schnittstellen für die Date-Objekte. | Bibliothek |
| **EventManager.Logic**         | In diesem Projekt sind alle Schnittstellen und der Datenzugriff definiert. | Bibliothek |
| EventManager.Logic.Contracts   | In diesem Abschnitt befinden sich alle Schnittstellen. | Bibliothek |
| EventManager.Logic.DataContext | In diesem Abschnitt befindet sich der Data-Kontext (`EventManagerContext`). | Bibliothek |
| **EventManager.ConApp**        | Konsolenanwendung zum Starten des Programms und zur Implementierung des Menüsystems. Menüfunktionen sind mit *throw new NotImplementedException()* markiert. | Konsolenanwendung |

---

## Datenstruktur

| Komponente   | Beschreibung                                 | Größe | Mussfeld | Eindeutig |
| ------------ | -------------------------------------------- | ----- | -------- | --------- |
| **Event**    | Eine Veranstaltung, die organisiert wird.    |       |          |           |
| *Title*      | Titel der Veranstaltung                      | 256   | Ja       | Ja        |
| *Description*| Beschreibung der Veranstaltung               | 1024  | Nein     | Nein      |
| *Date*       | Datum und Uhrzeit der Veranstaltung          | DateTime | Ja    | Nein      |
| *LocationId* | Fremdschlüssel zur Location                  | int   | Ja       | Nein      |
| **Location** | Der Veranstaltungsort                        |       |          |           |
| *Name*       | Name der Location                            | 256   | Ja       | Ja        |
| *Address*    | Adresse der Location                         | 512   | Ja       | Nein      |
| **Attendee** | Ein Teilnehmer einer Veranstaltung           |       |          |           |
| *EventId*    | Fremdschlüssel zur Veranstaltung             | int   | Ja       | Nein      |
| *FirstName*  | Vorname des Teilnehmers                      | 64    | Ja       | Nein      |
| *LastName*   | Nachname des Teilnehmers                     | 64    | Ja       | Nein      |
| *Email*      | E-Mail-Adresse des Teilnehmers               | 128   | Ja       | Ja        |

## Objektmodell und Beziehungen

|  Komponente  | Relation | Komponente |
|--------------|----------|------------|
| **Event**    | 1:n      | Attendee   |
| **Event**    | 1:1      | Location   |
| **Attendee** | 1:1      | Event      |
| **Location** | 1:n      | Event      |

---

## Aufgabenstellung

1. **Implementiere die Konsolenanwendung** mit folgenden Funktionen:
   - Eine Veranstaltung anlegen, bearbeiten und löschen.
   - Eine Location anlegen und bearbeiten.
   - Teilnehmer zu einer Veranstaltung hinzufügen.
   - Teilnehmerliste für eine Veranstaltung anzeigen.
   - Alle Veranstaltungen eines bestimmten Tages abrufen.
   - Eine Liste aller Veranstaltungen mit zugehöriger Location anzeigen.

2. **Entwickle die Datenlogik in `EventManager.Logic`**:
   - Implementiere CRUD-Methoden für `Event`, `Location` und `Attendee`.

3. **Implementiere den Datenzugriff in `EventManager.Logic.DataContext`**:
   - Nutze eine Datenbank zur Speicherung der Events, Locations und Teilnehmer.

4. **(Optional) Entwickle eine WebAPI als zusätzliche Schnittstelle**.

---

## Hilfsmittel

- Die 'CompanyManager'-Vorlage und die dokumentierten Demos. Sie finden die Vorlage [hier](https://github.com/leoggehrer/CompanyManager-Template).

## Abgabe

- Termin: 1 Woche nach der Ausgabe
- Klasse:
- Name:

## Quellen

- keine Angabe

> **Viel Erfolg!**
