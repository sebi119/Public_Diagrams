# Enhanced PlantUML Beispiele

Umfangreichere Diagramme mit fortgeschrittenen Features:
**Themes** (`!theme`), `skinparam`, Farbgebung, `autonumber`, Swimlanes,
`group`/`alt`, Notes, Stereotypen, Generics und Nicht-UML-Diagramme.

## Inhalt

| Datei | Typ | Features |
|-------|-----|----------|
| `sequence_advanced.puml` | Sequenz | `!theme`, autonumber, activate, alt/group, farbige Notes |
| `class_advanced.puml`    | Klasse  | Generics, Interface, abstract, enum, Value Object, ortho |
| `activity_swimlanes.puml`| Aktivität | Swimlanes, fork/join, verschachtelte Bedingungen |
| `deployment.puml`        | Deployment | nodes, artifacts, cloud, queue, Stereotypen |
| `er_diagram.puml`        | ER | Crow-Foot-Notation, PK/FK, Kardinalitäten |
| `gantt.puml`             | Gantt | Zeitplan, Abhängigkeiten, Farben |
| `mindmap.puml`           | Mindmap | `@startmindmap`, Theme |
| `wbs.puml`               | WBS | `@startwbs`, Projektstruktur |
| `data.json.puml`         | JSON | `@startjson`, Datenvisualisierung |

## Hinweis
Diese Beispiele sind bewusst von den Basis-Beispielen im Stammverzeichnis
(`../diagrams/`) durch diesen `enhanced/`-Ordner getrennt.

Gantt, Mindmap, WBS und JSON benötigen eine aktuelle PlantUML-Version (>= 1.2020).