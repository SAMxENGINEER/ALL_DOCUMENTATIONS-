# User Journeys and Workflows

## Journey Catalog

1. Crop Recommendation Journey
2. District Intelligence Journey
3. Advisory Guidance Journey
4. Crop Rotation Journey
5. Policy Discovery Journey

## 1) Crop Recommendation Journey

### Objective

Help users obtain a practical ranked list of crop options using submitted context.

### Flow

```mermaid
flowchart TD
    A[Open Recommendation Page] --> B[Select District]
    B --> C[Provide Farming Inputs]
    C --> D[Submit Request]
    D --> E[Process Recommendation Workflow]
    E --> F[Return Ranked Crops]
    F --> G[Render Results with Context]
```

### User Decisions Supported

- Compare top crop options.
- Choose next action: advisory follow-up or rotation planning.

## 2) District Intelligence Journey

### Objective

Provide planning context for a selected district.

### Flow

```mermaid
flowchart TD
    A[Open Dashboard] --> B[Pick District]
    B --> C[Load District Payload]
    C --> D[Show Region Summary]
    D --> E[Show Climate Risk Highlights]
    E --> F[Show Sowing and Yield Sections]
    F --> G[Support District-Level Planning]
```

### User Decisions Supported

- Understand local planning context.
- Align crop planning with district conditions.

## 3) Advisory Guidance Journey

### Objective

Provide follow-up guidance in response to user questions.

### Flow

```mermaid
flowchart TD
    A[Open Advisory Panel] --> B[Enter Question]
    B --> C[Attach District Context]
    C --> D[Optional Crop Context]
    D --> E[Generate Advisory Output]
    E --> F[Display Guidance]
```

### User Decisions Supported

- Clarify recommended actions.
- Translate recommendation into field-level next steps.

## 4) Crop Rotation Journey

### Objective

Recommend next crop direction based on previously grown crop.

### Flow

```mermaid
flowchart TD
    A[Open Rotation Planner] --> B[Select Last Crop]
    B --> C[Compute Rotation Sequence]
    C --> D[Present Next Crop]
    D --> E[Show Rotation Rationale]
    E --> F[Enable Season Continuity Planning]
```

### User Decisions Supported

- Plan what to grow next.
- Understand continuity logic between seasons.

## 5) Policy Discovery Journey

### Objective

Help users identify relevant support schemes and access channels.

### Flow

```mermaid
flowchart TD
    A[Open Policy Advisor] --> B[Choose Policy Category]
    B --> C[Review Scheme Card]
    C --> D[Check Eligibility]
    D --> E[Review Benefits]
    E --> F[Open Official Access Link]
```

### User Decisions Supported

- Identify suitable support programs.
- Move from awareness to application channel.

## Cross-Journey Transition Map

```mermaid
graph LR
    H[Home] --> R[Recommendation]
    H --> D[Dashboard]
    H --> P[Policy Advisor]

    R --> RS[Results]
    RS --> A[Advisory]
    RS --> ROT[Rotation]

    D --> R
    P --> R
```

## Lifecycle State View

```mermaid
stateDiagram-v2
    [*] --> Discover
    Discover --> Input
    Input --> Evaluate
    Evaluate --> Recommend
    Recommend --> Advise
    Recommend --> Rotate
    Advise --> Act
    Rotate --> Act
    Act --> [*]
```

## Journey Design Notes

- Journeys are independent yet connected.
- Recommendation and results act as the central decision hub.
- District and policy journeys can be entered directly or used as support context.
