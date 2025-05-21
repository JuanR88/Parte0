sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Escribe una nota y hace clic en "Save"
    Note right of browser: JS captura el evento del formulario

    browser->>server: POST /new_note_spa con la nota en JSON
    activate server
    server->>server: Guardar la nota
    server-->>browser: Respuesta JSON (nota guardada)
    deactivate server

    Note right of browser: JS actualiza el DOM sin recargar la página

    browser-->>user: Muestra la nueva nota en la lista
