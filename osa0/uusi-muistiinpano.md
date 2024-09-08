# Kaavio-0.4: uusi muistiinpano

**Kayttaja luo uuden muistiinpanon
**

``` mermaid
sequenceDiagram
    participant browserK
    participant serverH

    browserK->>serverH: POST https://studies.cs.helsinki.fi/exampleapp/new_notes
    activate serverH
    serverH-->>browserK: REDIRECT (refer) to https://studies.cs.helsinki.fi/exampleapp/notes
    deactivate serverH
    Note left of serverH: server to save the new value

    browserK->>serverH: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate serverH
    serverH-->>browserK: HTML document
    deactivate serverH
    
    browserK->>serverH: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate serverH
    serverH-->>browserK: the css file
    deactivate serverH
    
    browserK->>serverH: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate serverH
    serverH-->>browserK: the JavaScript file
    deactivate serverH
    
    Note right of browserK: The browserK starts executing the JavaScript code that fetches the JSON from the serverH
    
    browserK->>serverH: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate serverH
    serverH-->>browserK: [{"content":"","date":"2024-09-05T20:17:36.053Z"}...]
    deactivate serverH    

    Note right of browserK: The browserK executes the callback function that renders the notes
```
