# Projektplan – Software-Release (Gantt)

> Mermaid-Version von [`gantt.puml`](gantt.puml).
> Hinweis: Mermaid kann „after" nur auf **eine** Vorgängeraufgabe beziehen –
> Integration ist daher an die längere Aufgabe (Backend) gehängt.

```mermaid
gantt
    title Projektplan – Software-Release
    dateFormat  YYYY-MM-DD
    section Planung
    Anforderungsanalyse :req, 2026-07-01, 5d
    Architekturdesign   :arch, after req, 4d
    section Entwicklung
    Backend-Entwicklung :be, after arch, 12d
    Frontend-Entwicklung:fe, after arch, 10d
    section Integration & Test
    Integration :int, after be, 5d
    Testing     :test, after int, 6d
    Release     :milestone, rel, after test, 0d
```