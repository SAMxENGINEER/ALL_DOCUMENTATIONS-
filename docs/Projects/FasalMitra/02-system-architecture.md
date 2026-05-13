# System Architecture

## Architecture Summary

The platform follows a two-tier architecture:

- **Frontend Application Layer** for user interaction and journey orchestration.
- **Backend Service Layer** for recommendation logic, advisory generation, and district data delivery.

## Component Topology

```mermaid
graph TB
    subgraph Client Side
      UI[Web Application]
      Pages[Feature Pages]
      Components[Reusable UI Components]
    end

    subgraph Service Side
      API[HTTP API Layer]
      Predict[Recommendation Service]
      Advisory[Advisory Service]
      District[District Information Service]
      Support[Support Services]
    end

    UI --> Pages --> Components
    UI --> API
    API --> Predict
    API --> Advisory
    API --> District
    Predict --> Support
    Advisory --> Support
    District --> Support
```

## Runtime Interaction Model

1. User actions in the web interface trigger feature-specific API calls.
2. API layer routes requests to dedicated domain services.
3. Services assemble contextual outputs and return normalized responses.
4. Frontend renders recommendation, advisory, and district outcomes.

## Request Lifecycle Flow

```mermaid
sequenceDiagram
    participant User
    participant Frontend
    participant API
    participant Service

    User->>Frontend: Submit feature input
    Frontend->>API: Send structured request
    API->>Service: Execute domain workflow
    Service-->>API: Return computed response
    API-->>Frontend: Send response payload
    Frontend-->>User: Render actionable output
```

## Cross-Cutting Concerns

- Unified API access model for all major product capabilities.
- Consistent district-context behavior across recommendation and advisory experiences.
- Shared language-aware interface behavior for multilingual usability.
