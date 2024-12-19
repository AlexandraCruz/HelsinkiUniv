# HelsinkiUniv

Advanced Modern Web App update 2025

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Write note and click Save
    Browser->>Server: HTTP POST /new_note
    Server-->>Browser: HTTP 302 Redirect to /notes
    Browser->>Server: HTTP GET /notes
    Browser->>Server: HTTP GET /main.css
    Browser->>Server: HTTP GET /main.js
    Browser->>Server: HTTP GET /data.json
    Note right of Server: Server processes POST request
    Note right of Server: Server creates new note object
    Note right of Server: Server adds note to notes array
    Note right of Server: Notes are not saved to database
