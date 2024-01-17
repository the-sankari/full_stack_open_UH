```````mermaid
sequenceDiagram
    participant browser
    participant server
    participant spa

    Note right of browser: User navigates to https://studies.cs.helsinki.fi/exampleapp/spa

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: SPA HTML document
    deactivate server

    Note right of browser: Browser starts loading SPA resources

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: SPA CSS file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: SPA JavaScript file
    deactivate server

    Note right of browser: SPA JavaScript code fetches data asynchronously

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{content: "kajol was here", date: "2024-01-17T20:35:12.936Z"}, ... ]
    deactivate server

    Note right of browser: SPA renders notes on the page

    browser->>spa: Render notes using JavaScript
    activate spa
    spa-->>browser: Notes rendered on the page
    deactivate spa
    ``````
```````
