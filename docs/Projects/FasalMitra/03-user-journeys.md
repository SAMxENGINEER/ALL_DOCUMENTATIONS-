# User Journeys and Workflows

## Journey 1: Crop Recommendation

This journey supports users in obtaining a ranked set of crop options with current context.

```mermaid
flowchart TD
    A[Open Recommendation Page] --> B[Provide District and Farming Inputs]
    B --> C[Submit Recommendation Request]
    C --> D[System Evaluates Inputs and Context]
    D --> E[Ranked Crop Recommendations Returned]
    E --> F[Results Page with Weather and Advisory Access]
```

## Journey 2: District Intelligence Review

This journey supports district-level planning and seasonal awareness.

```mermaid
flowchart TD
    A[Open District Dashboard] --> B[Select District]
    B --> C[Fetch District Intelligence]
    C --> D[Display Region Summary]
    D --> E[Show Risk Highlights]
    E --> F[Show Sowing and Yield Insights]
```

## Journey 3: Advisory Interaction

This journey supports targeted question-based guidance.

```mermaid
flowchart TD
    A[Open Advisory Panel] --> B[Enter Question]
    B --> C[Attach District and Optional Crop Context]
    C --> D[Generate Advisory Response]
    D --> E[Stream Response to User]
```

## Journey 4: Crop Rotation Planning

This journey helps users identify next-season crop continuity.

```mermaid
flowchart TD
    A[Open Rotation Planner] --> B[Select Previous Crop]
    B --> C[Build Rotation Chain]
    C --> D[Present Recommended Next Crop]
    D --> E[Explain Rotation Reasoning]
```

## Journey 5: Policy Discovery

This journey helps users identify support schemes and official channels.

```mermaid
flowchart TD
    A[Open Policy Advisor] --> B[Filter by Scheme Category]
    B --> C[Review Scheme Details]
    C --> D[Check Eligibility and Benefit]
    D --> E[Follow Official Access Link]
```

## End-to-End Multi-Journey Map

```mermaid
graph LR
    H[Home] --> R[Recommendation]
    H --> D[Dashboard]
    H --> P[Policy Advisor]
    R --> RS[Results]
    RS --> A[Advisory]
    RS --> RP[Rotation Planner]
```
