

```mermaid
sequenceDiagram
    participant U
    participant CTC
    participant CSV
    participant GAME
    participant IC

    U->>CTC: Logs in
    U->>CTC: Navigate to CSV
    CTC->>CSV: Open CSV Window
    CSV->>GAME: Ask for User Data
    Note right of CSV: REST API (achievements + ranking)
    GAME-->>CSV: Return User Data
    CSV->>IC: Ask for User Data
    Note right of CSV: REST API (achievements + ranking)
    IC-->>CSV: Return for User Data
    CSV->>U: Displays Visualisations
```
