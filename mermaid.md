##Sequence Diagram
```mermaid
    sequencediagram;
      participant browser;
      participant server;
      participant user;
      browser --> server : GET https://studies.cs.helsinki.fi/exampleapp/notes;
      activate server;
      server --> browser : HTML document;
      deactivate server;
```
