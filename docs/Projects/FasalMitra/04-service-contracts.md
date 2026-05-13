# Service Contracts

## Contract Style

All service interactions use clear request/response contracts over HTTP. Responses are normalized for frontend rendering and user decision clarity.

## Endpoint Catalog

- `GET /api/health`
- `POST /api/predict`
- `POST /api/advisory`
- `GET /api/district/{district_name}`

## Contract Diagram

```mermaid
graph TD
    C[Client] --> H[/GET /api/health/]
    C --> P[/POST /api/predict/]
    C --> A[/POST /api/advisory/]
    C --> D[/GET /api/district/district_name/]

    P --> PR[Recommendation Response]
    A --> AR[Advisory Response]
    D --> DR[District Response]
    H --> HR[Service Status]
```

## Health Contract

### Request

- Method: `GET`
- Path: `/api/health`

### Response

- Status indicator payload confirming service readiness.

## Recommendation Contract

### Request

- Method: `POST`
- Path: `/api/predict`
- Expected conceptual fields:
  - District context
  - Soil/farming inputs
  - Seasonal selection behavior

### Response

- District label and current month context.
- Weather context summary.
- Ranked recommendation list with reasoning metadata.

## Advisory Contract

### Request

- Method: `POST`
- Path: `/api/advisory`
- Expected conceptual fields:
  - Farmer question
  - District context
  - Optional crop context

### Response

- Text advisory output designed for practical field interpretation.

## District Information Contract

### Request

- Method: `GET`
- Path: `/api/district/{district_name}`

### Response

- District intelligence payload including planning-oriented regional context.

## Interaction Sequence for Recommendation + Advisory

```mermaid
sequenceDiagram
    participant User
    participant Frontend
    participant PredictAPI as Predict Endpoint
    participant Results
    participant AdvisoryAPI as Advisory Endpoint

    User->>Frontend: Submit recommendation input
    Frontend->>PredictAPI: POST /api/predict
    PredictAPI-->>Frontend: Ranked recommendations
    Frontend->>Results: Render results view
    User->>Frontend: Ask follow-up advisory question
    Frontend->>AdvisoryAPI: POST /api/advisory
    AdvisoryAPI-->>Frontend: Advisory text response
```
