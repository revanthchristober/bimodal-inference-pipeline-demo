
# POC: Blue-Green Deployment Pipeline for Inference

This POC demonstrates the CI/CD pipeline for a zero-downtime, blue-green deployment strategy for a real-time ML inference service.

## Architecture

```mermaid
graph TD
    A[Start Deploy] --> B{Deploy Green Candidate};
    B --> C{Run Perf Tests};
    C -- Pass --> D{Promote Green to Live};
    D --> E[Live Traffic to Green];
    C -- Fail --> F[Alert & Rollback];
    D --> G{Teardown Old Blue};
```
```