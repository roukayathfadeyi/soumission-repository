sequenceDiagram
  participant browser
  participant server

  /*L'utilisateur entre une note dans le champ texte et clique sur "Envoyer"*/
  
  browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
  activate server
  /*Note right of browser: Le serveur reçoit les données du formulaire envoyé par l'utilisateur*/
  server-->>browser: HTTP 302 Redirect vers /exampleapp/notes
  deactivate server

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
  activate server
  server-->>browser HTML document
  deactivate server

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
  activate server
  server-->>browser: the css file
  deactivate server
  
  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
  activate server
  server-->>browser: the JavaScript file
  deactivate server

  /*Note right of browser: Le navigateur exécute le JavaScript qui charge les notes*/
  
  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate server
  server-->>browser: [{"content":ma note", "date":'2026-5-7"},....]
  deactivate server
        
  /*Note right of browser: Le navigateur re-affiche toutes les notes dont la nouvelle*/


  

  
