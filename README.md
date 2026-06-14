# PlantUML Beispiele


**VS Code:** Extension "PlantUML" (jebbs) installieren, dann `Alt+D` zum Vorschauen.


Eine Sammlung von PlantUML-Diagrammen als Lern- und Referenzbeispiele.

## Inhalt

| Datei | Diagrammtyp |
|-------|-------------|
| `diagrams/sequence.puml`  | Sequenzdiagramm (Login-Flow) |
| `diagrams/class.puml`     | Klassendiagramm (Domänenmodell) |
| `diagrams/usecase.puml`   | Anwendungsfalldiagramm |
| `diagrams/activity.puml`  | Aktivitätsdiagramm (Bestellprozess) |
| `diagrams/component.puml` | Komponentendiagramm (Architektur) |
| `diagrams/state.puml`     | Zustandsdiagramm (Ticket-Lebenszyklus) |

## Rendern

**Online:** Inhalt nach <https://www.plantuml.com/plantuml> kopieren.

**Lokal (benoetigt Java + Graphviz):**
```bash
java -jar plantuml.jar diagrams/*.puml
```

