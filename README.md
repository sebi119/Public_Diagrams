# PlantUML & Mermaid Beispiele

Eine Sammlung von Diagrammen als Lern- und Referenzbeispiele – jeweils in **zwei Formaten**:

- **`.puml`** (PlantUML): höchste Qualität, rendert in VS Code / plantuml.com, **aber NICHT auf GitHub**.
- **`.md`** (Mermaid): **rendert direkt hier auf GitHub** im Browser.

> GitHub unterstützt Mermaid nativ in Markdown, PlantUML jedoch nicht. Darum gibt es zu jedem
> Diagramm eine Mermaid-Variante als `.md`-Datei.

## Basis-Diagramme

| Thema | PlantUML | Mermaid (GitHub) |
|-------|----------|------------------|
| Sequenz – Login | [`diagrams/sequence.puml`](diagrams/sequence.puml) | [`diagrams/sequence.md`](diagrams/sequence.md) |
| Klasse – Onlineshop | [`diagrams/class.puml`](diagrams/class.puml) | [`diagrams/class.md`](diagrams/class.md) |
| Use Case – Bibliothek | [`diagrams/usecase.puml`](diagrams/usecase.puml) | [`diagrams/usecase.md`](diagrams/usecase.md) |
| Aktivität – Bestellprozess | [`diagrams/activity.puml`](diagrams/activity.puml) | [`diagrams/activity.md`](diagrams/activity.md) |
| Komponente – Architektur | [`diagrams/component.puml`](diagrams/component.puml) | [`diagrams/component.md`](diagrams/component.md) |
| Zustand – Ticket | [`diagrams/state.puml`](diagrams/state.puml) | [`diagrams/state.md`](diagrams/state.md) |

> Die umfangreicheren Beispiele unter [`enhanced/`](enhanced/) haben jeweils ihre eigene
> Mermaid-`.md`-Datei, werden hier aber nicht eingebettet.

---

## Vorschau (rendert direkt auf GitHub)

### Sequenz – Login-Ablauf
```mermaid
sequenceDiagram
    actor Benutzer
    participant Web as Web-App
    participant Auth as Auth-Service
    participant DB
    Benutzer->>Web: Anmeldedaten eingeben
    Web->>Auth: POST /login
    Auth->>DB: Benutzer prüfen
    DB-->>Auth: Benutzerdatensatz
    alt Gültige Anmeldedaten
        Auth-->>Web: JWT-Token
        Web-->>Benutzer: Weiterleitung zum Dashboard
    else Ungültig
        Auth-->>Web: 401 Unauthorized
        Web-->>Benutzer: Fehlermeldung anzeigen
    end
```

### Klasse – Domänenmodell
```mermaid
classDiagram
    class Kunde {
      +Long id
      +String name
      +bestellen() Bestellung
    }
    class Bestellung {
      +Long id
      +BigDecimal gesamt()
    }
    class Position {
      +int menge
    }
    class Produkt {
      +String bezeichnung
      +BigDecimal preis
    }
    Kunde "1" --> "*" Bestellung : tätigt
    Bestellung "1" *-- "*" Position : enthält
    Position "*" --> "1" Produkt : verweist auf
```

### Use Case – Bibliothek
```mermaid
flowchart LR
    Leser((Leser))
    Bibliothekar((Bibliothekar))
    subgraph Bibliothekssystem
      UC1([Buch suchen])
      UC2([Buch ausleihen])
      UC3([Buch zurückgeben])
      UC4([Bestand verwalten])
      UC6([Mitgliedschaft prüfen])
    end
    Leser --- UC1
    Leser --- UC2
    Leser --- UC3
    Bibliothekar --- UC4
    UC2 -. include .-> UC6
```

### Aktivität – Bestellprozess
```mermaid
flowchart TD
    Start([Start]) --> A[Warenkorb prüfen]
    A --> B{Artikel verfügbar?}
    B -- ja --> C[Zahlung verarbeiten]
    B -- nein --> D[Nachbestellung anbieten] --> S1([Stop])
    C --> E{Zahlung erfolgreich?}
    E -- ja --> F[Bestellung bestätigen] --> G[Versand veranlassen] --> H[Bestätigung senden] --> S2([Stop])
    E -- nein --> I[Zahlung ablehnen] --> S3([Stop])
```

### Komponente – Architektur
```mermaid
flowchart TD
    subgraph Frontend
      WC[Web-Client]
      MA[Mobile-App]
    end
    subgraph Backend
      GW[API-Gateway]
      AUTH[Auth-Service]
      ORD[Order-Service]
    end
    DB[(PostgreSQL)]
    PAY[Zahlungsanbieter]
    WC -->|HTTPS| GW
    MA -->|HTTPS| GW
    GW --> AUTH
    GW --> ORD
    ORD --> DB
    ORD -->|REST| PAY
```

### Zustand – Ticket-Lebenszyklus
```mermaid
stateDiagram-v2
    [*] --> Offen
    Offen --> InBearbeitung : zuweisen
    InBearbeitung --> Wartend : Rückfrage
    Wartend --> InBearbeitung : Antwort erhalten
    InBearbeitung --> Gelöst : Lösung
    Gelöst --> Geschlossen : bestätigt
    Gelöst --> InBearbeitung : erneut geöffnet
    Geschlossen --> [*]
```

---

## PlantUML rendern (`.puml`)

- **Online:** Inhalt nach <https://www.plantuml.com/plantuml> kopieren.
- **Lokal (Java + Graphviz):** `java -jar plantuml.jar diagrams/*.puml`
- **VS Code:** Extension „PlantUML" (jebbs), dann `Alt+D` zur Vorschau.