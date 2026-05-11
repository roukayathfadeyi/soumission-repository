sequenceDiagram
  participant browser
  participant server

  browser->>: GET https://studies.cs.helsinki.fi/exampleapp/spa
  activate server
  server-->>browser: HTML document
  deactivate server

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
  activate server
  server-->>browser: the css file
  deactivate server

  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
  activate server
  server-->>browser: the JavaScript file
  deactivate server

  /*Le navigateur exécute spa.js qui charge les notes via fetch()*/
  browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate server
  server-->>browser: [{"content": "HTML is easy", "date": "2019-1-1"},....]
  deactivate server

  /*Le navigaeur affiche les notes sans recharger la page*/
