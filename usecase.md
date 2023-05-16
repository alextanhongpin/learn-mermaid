# How to document Usecase?

We can use either

- sequence diagram
- flowchart

```mermaid
---
title: User login flow
---
sequenceDiagram
    autonumber
    actor p0 as Alice
    participant web0 as Website
    participant ms0 as Auth Service

    p0 ->> web0: navigates to Login Page
    web0 ->> web0: submits email and password
    web0 ->> +ms0: POST /login    
    ms0 -->> -web0: 200 - OK
    web0 -->> p0: 303 - Redirect
```

## Do we need to show all the possible errors/failure case? 

Nope, just write them separately as text, e.g. in the diagram above, we have the numbering for each steps. So we can use `A1, A2, ... AN` to indicate **alternative** paths.

- A1. Page not found? End usecase
- A2. Email or password not provided or invalid? Show error message.
- A3. Service is down? Show error message


## Sometimes representing it as table is more convenient

| Flow | Alternative |
| -- | -- | 
| 1. User navigates to Login Page | A1. Page not found |
| 2. User submits email and password | A2. Email or password not provided or invalid? Show error message. |
| 3. Client sends the request to the system | A3. Service is down? Show error message |
| 4. System logins the user and returns access token | A4. User not found? Return error | 
| 5. System redirects the user to the home page | |
