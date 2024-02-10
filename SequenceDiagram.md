sequenceDiagram
    participant browser
    participant server
    participant database

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server->>database: Save new note data
    activate database
    database-->>server: Confirmation
    deactivate database
    server-->>browser: Redirect to notes page
    deactivate server
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: Updated notes list
    deactivate server
