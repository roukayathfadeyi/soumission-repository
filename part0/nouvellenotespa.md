sequenceDiagram
  participant browser
  participant server
  /*L'utilisateur écrit dans le champs text et clique sur "Envoyer".
  spa.js intercepte l'évenement et empêche le rechargement de la page.*/
  
  browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
  activate server
  /*Le serveur reçoit les données en JSON : {"content:"ma note", "date":"2026-05-11*/
  server-->>browser: HTTP 201 Created {"message":"note created"}
  deactivate server
  /*Le navigateur ajoute la nouvelle note localement et met à jour le DOM sans recharger la page*</
  
