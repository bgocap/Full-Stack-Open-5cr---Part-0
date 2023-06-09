Exercise 0.4

```mermaid
sequenceDiagram
    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Browser: HTML document
    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser:CSS File
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/main.js
    rect rgb(191, 223, 255)
        Server-->>Browser:JavaScript file
        Note over Browser,Server: The browser starts executing the JavaScript code that fetches <br/>the JSON from the server
    end
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/data.json
    rect rgb(191, 223, 255)
        Server-->>Browser:[{content: 'notee', date: '2023-06-05T14:08:40.353Z'},...]
        Note over Browser,Server: The browser executes the callback function that renders the notes.
    end
    rect rgb(191, 223, 255)
        Note over Browser,Server: User wrote in the text box: "aaa", <br/>and then pressed submit which creates a request to the server.
        Browser->>Server:POST https://studies.cs.helsinki.fi/exampleapp/new_note
    end
    rect rgb(191, 223, 255)
        Server-->>Browser:HTTP status code 302 -> RELOAD
        Note over Browser,Server: This means that the request is <br/>done and the browser should reload.
    end
    
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Browser: HTML document
    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser:CSS File
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>Browser:JavaScript file
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/data.json
    rect rgb(191, 223, 255)
        Server-->>Browser:[{content: 'notee', date: '2023-06-05T14:08:40.353Z'},...,<br/>{content: 'aaa', date: '2023-06-05T16:12:42.227Z'},...]
        Note over Browser,Server: The browser executes the callback function that renders the notes <br/> including the new one we submited.
    end
```

Excersise 0.5

```mermaid
sequenceDiagram
    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    Server-->>Browser: HTML document
    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser:CSS File
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    rect rgb(191, 223, 255)
        Server-->>Browser:JavaScript file
        Note over Browser,Server: The browser starts executing the JavaScript code that fetches <br/>the JSON from the server
    end
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/data.json
    rect rgb(191, 223, 255)
        Server-->>Browser:[{content: "", date: "2023-06-06T10:13:25.850Z"},…]
        Note over Browser,Server: The browser executes the callback function that renders the notes.
    end
```

Excersise 0.6

```mermaid
sequenceDiagram
    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    Server-->>Browser: HTML document
    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser:CSS File
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    rect rgb(191, 223, 255)
        Server-->>Browser:JavaScript file
        Note over Browser,Server: The browser starts executing the JavaScript code that fetches <br/>the JSON from the server
    end
    Browser->>Server:GET https://studies.cs.helsinki.fi/exampleapp/data.json
    rect rgb(191, 223, 255)
        Server-->>Browser:[{content: "notee", date: "2023-06-05T14:08:40.353Z"},…]
        Note over Browser,Server: The browser executes the callback function that renders the notes.
    end
    rect rgb(191, 223, 255)
        Note over Browser,Server: User wrote in the text box: "test2", <br/> then pressed submit which adds the user input straight  to the browser <br/> and makes the request to the server for only insert the user's input.
        Browser->>Server:POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    end
    rect rgb(191, 223, 255)
        Server-->>Browser:HTTP status code 201
        Note over Browser,Server: This means that the request is done, but this time the page doesn't reload.
    end
```
