# Part 0, 0.6 New note in Single page app diagram

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Write note and click Save
    Browser->>Server: HTTP POST /new_note
    Server-->>Browser: HTTP 201 Created
    Note right of Server: Server processes POST request
    Note right of Server: Server creates new note object
    Note right of Server: Server updates in-memory data store

    Browser->>Browser: Update UI with new note
