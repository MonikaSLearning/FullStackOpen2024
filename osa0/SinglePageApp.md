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

```
