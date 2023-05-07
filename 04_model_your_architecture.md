# Model Your Architecture

Using C4 model:
- system context
- container
- component
- code


## Creating a System Context Diagram

```mermaid
---
title: "Listing Service C4 Model: System Context"
---
%% TD: top-down
flowchart TD
    %% Each node should contain a title, label and description.
    User["
        Premium Member
        [Person]

        A user of the website who has
        purchased a subscription
    "]

    LS["
        Listing Service
        [Software System]

        Serves web pages displaying title
        listings to the end user
    "]

    TS["
        Title Service
        [Software System]

        Provides an API to retrieve
        title information
    "]

    RS["
        Review Service
        [Software System]

        Provides an API to retrieve
        and submit reviews
    "]

    SS["
        Search Service
        [Software System]

        Provides an API to search
        for titles
    "]

    User -- "Views titles, searches titles\nand reviews title using" --> LS
    LS -- "Retrieves title\ninformation from" --> TS
    LS -- "Retrieves from and\nsubmits reviews to" --> RS
    LS -- "Searches for titles\nusing" --> SS

    %% Define classes using syntax "classDef className styleProperties".
    classDef focusSystem fill:#1168bd,stroke:#0b4884,color:white
    classDef supportingSystem fill:#666,stroke:#0b4884,color:white
    classDef person fill:#08427b,stroke:#052e56,color:white

    %% Apply style using syntax "class nodeId(s) className".
    class LS focusSystem
    class TS,RS,SS supportingSystem
    class User person
```
