``mermaid
sequenceDiagram
    participant browser
    participant server
    participant user

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
    user ->> browser : input data
    user ->> browser : click on save button
    Note right of browser : The browser sends the input data to the server.
    browser ->> server : POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Note right of browser : The server appends the data to the payload.
    server -->> browser : HTTPS Status code of 302 and a URL Redirect.
    browser ->> server : GET /exampleapp/notes HTTP/1.1
    server -->> browser : HTML Document
    Note right of browser : The browser displays a updated HTML document with uploaded notes.
```
