#### UC-A-04: Challenge – Labs – Exercises visualizations

- Scenario network graph (Req-094) 
- VM details pop-up on network graph (Req-095) 
- Difficulty ratings from users graph (Req-096) 
- Times played and Outcomes over time graph (Req-097) 

```mermaid
sequenceDiagram
    participant U as U1, U2, U3, U4, U5
    participant CTC
    participant CSV
    participant TBD1 as IC
    participant TBD2 as DSC
    participant GAME

    U->>CTC: Logs in
    U->>CSV: Asks for Available Scenarios

    CSV->>TBD1: Get List of Available Scenarios
    Note right of CSV: REST API
    TBD1-->>CSV: List of Available Scenarios

    CSV-->>U: List of Available Scenarios
    U->>CSV: User Selects Scenario of Interest

    CSV->>TBD2: Get Scenario Specification
    Note right of CSV: REST API
    TBD2-->>CSV: Returns Scenario Specification

    CSV->>GAME: Get User Ratings for Scenario
    Note right of CSV: REST API
    GAME-->>CSV: Returns User Ratings for Scenario

    CSV->>GAME: Get Scenario Outcome Statistics
    Note right of CSV: REST API
    GAME-->>CSV: Returns Scenario Outcome Statistics

    CSV->>U: Displays Scenario Visualisations
```
