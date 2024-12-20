# Part 0, 0.4 New Note Diagram

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Write note and click Save
    Browser->>Server: HTTP POST /new_note
    Server-->>Browser: HTTP 302 Redirect to /notes
    Browser->>Server: HTTP GET /notes
    Server-->>Browser: HTML page with list of notes

    Note right of Server: Server processes POST request
    Note right of Server: Server creates new note object
    Note right of Server: Server adds note to database
    Note right of Server: Server renders HTML page with updated note list
