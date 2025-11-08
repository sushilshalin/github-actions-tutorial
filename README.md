# github-actions-tutorial
this is repo to test and learn github actions
hi


flowchart TD
    Client((Client))
    TestCopilotController["TestCopilotController"]
    AggregatorController["AggregatorController"]
    AggregatorService["AggregatorService"]
    AggregatorRepository["AggregatorRepository"]
    Redis[(Redis)]
    PubSub[(Google Pub/Sub)]
    PostgreSQL[(PostgreSQL)]

    Client -->|HTTP Request| TestCopilotController
    Client -->|HTTP Request| AggregatorController
    AggregatorController -->|Business Logic| AggregatorService
    AggregatorService -->|DB Ops| AggregatorRepository
    AggregatorRepository -->|Read/Write| PostgreSQL
    AggregatorService -->|Cache Ops| Redis
    AggregatorService -->|Publish| PubSub
    AggregatorService -->|Return Data| AggregatorController
    AggregatorController -->|HTTP Response| Client
    TestCopilotController -->|HTTP Response| Client
