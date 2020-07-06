#### UC-A-03: System visualizations

- Active users and teams over time plot (Req-083) 
- Users per weekday plot (Req-084) 
- Users per hour of day plot (Req-085) 
- Users per month plot (Req-086) 
- Users per challenge category plot (Req-088) 

```mermaid
sequenceDiagram
    participant U as U1, U2, U3, U4, U5
    participant CTC
    participant CSV as CSV
    participant CTC_Auth as CTC/Auth

    par Get Data
        CSV->>CTC_Auth: A Database that keeps Usage data
        Note right of CSV: REST API
        CTC_Auth-->>CSV: Return Usage data (Source 1)
    end

    U->>CTC: Logs in
    U->>CTC: Navigate to CSV
    CTC->>CSV: Open CSV Window
    CSV-->>U: CSV Window

    U ->>CSV: Ask for system visualisations
    CSV-->>CSV: Query Internal Database
    CSV->>U: Displays Visualisations
```
