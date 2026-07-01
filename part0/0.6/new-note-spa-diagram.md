```mermaid
sequenceDiagram
    participant browser
    participant server

    Note left of server: This SPA version, when we submit the form, executes the JavaScript code by fetching the existing notes, then registering an event handler that prevents the previous default execution.  
    Note left of server: A new note is then created with the form data, appends it to the existing list of notes, rerenders the notes list on the page and sends the new note to the server with a POST request as a JSON string.

    browser->>server: POST [https://studies.cs.helsinki.fi/exampleapp/new_note_spa]
    activate server
    server-->>browser: JSON Response: {"message":"note created"}, HTTP code 201 (created)
    deactivate server

