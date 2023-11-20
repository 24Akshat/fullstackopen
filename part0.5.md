```mermaid
sequenceDiagram
    participant user
    participant browser
    participant server

    user ->> browser : Opens the browser
    user ->> browser : Enters the URL https://studies.cs.helsinki.fi/exampleapp/spa
    browser ->> server : GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server -->> browser : HTML Document
    deactivate server

    browser ->> server : GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server -->> browser : CSS Document
    deactivate server

    browser ->> server : GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server -->> browser : Javascript Document
    deactivate server

    Note on browser : The browser parses the Javasript Document and requests a JSON file
    browser ->> server : GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server -->> browser : JSON Array
    deactivate server
```
