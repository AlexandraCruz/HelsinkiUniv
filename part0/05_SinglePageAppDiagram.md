# Part 0, 0.5 Single Page App Diagram

```mermaid
sequenceDiagram
participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document (including references to main.css and main.js)
    deactivate server

    Note right of browser: Browser parses HTML, downloads referenced resources:
        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
        activate server
        server-->>browser: the css file
        deactivate server

        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
        activate server
        server-->>browser: the JavaScript file
        deactivate server

    Note right of browser: JavaScript code executes in the browser
        browser->>server: (asynchronous) GET https://studies.cs.helsinki.fi/exampleapp/data.json  // Fetches data after initial load
        activate server
        server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]  // JSON data with notes
        deactivate server

    Note right of browser: JavaScript processes data and renders the notes application
