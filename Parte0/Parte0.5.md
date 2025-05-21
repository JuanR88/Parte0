sequenceDiagram
    participant browser
    participant server

    browser->>server: GET /spa
    activate server
    server-->>browser: HTML (SPA)
    deactivate server

    browser->>server: GET /main.css
    server-->>browser: CSS file

    browser->>server: GET /spa.js
    server-->>browser: JavaScript (SPA)

    Note right of browser: El navegador ejecuta spa.js

    browser->>server: GET /data.json
    activate server
    server-->>browser: JSON con notas
    deactivate server

    Note right of browser: JS renderiza las notas sin recargar la página
