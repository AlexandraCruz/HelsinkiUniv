```mermaid
classDiagram
    class User
    class Browser
    class Server

    User "Write note and click Save" --> Browser
    Browser --> Server: HTTP POST /new_note
    Server --> Browser: HTTP 302 Redirect to /notes
    Browser --> Server: HTTP GET /notes
    Server --> Browser: HTTP GET /notes
    Browser --> Server: HTTP GET /main.css
    Server --> Browser: HTTP GET /main.css
    Browser --> Server: HTTP GET /main.js
    Server --> Browser: HTTP GET /main.js
    Browser --> Server: HTTP GET /data.json
    Server --> Browser: HTTP GET /data.json




    Server --> Server: Server processes POST request
    Server --> Server: Server creates new note object
    Server --> Server: Server adds note to notes array
    Server --> Server: Notes are not saved to database
