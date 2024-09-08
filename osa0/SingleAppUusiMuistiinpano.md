# Kaavio-0.5: Single Page App

**Kayttaja selaa muistiinpanoja
**

``` mermaid
sequenceDiagram
    participant browserK
    participant serverH
    browserK->>serverH: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate serverH
    serverH-->>browserK: HTML document
    deactivate serverH

    browserK->>serverH: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate serverH
    serverH-->>browserK: the css file
    deactivate serverH

    browserK->>serverH: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate serverH
    serverH-->>browserK: the js file
    deactivate serverH

    browserK->>serverH: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate serverH
    serverH-->>browserK: [ { "content": "","date": "2024-09-05T20:17:36.053Z"}....]
    deactivate serverH
    Note left of serverH: The content before adding and saving the new note

    browserK->>serverH: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa.json
    activate serverH
    serverH-->>browserK: [ {"message":"note created"}]
    deactivate serverH
    Note left of serverH: The new note is added and saved to the Notes content to be displayed

```
