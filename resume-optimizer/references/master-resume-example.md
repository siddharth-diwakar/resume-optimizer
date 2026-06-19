# Master Resume — Example (Jane Doe)

> This is a FILLED-IN EXAMPLE showing what "good" looks like.
> Don't edit this file — copy `master-resume.md` (the template) and fill that in with your real info.
> Use this as a depth/format reference: bullets have numbers, scope signals, and stack lists.

## Contact
- Name: Jane Doe
- Location: Austin, TX
- Email: jane.doe@example.com
- Phone: (512) 555-0142
- LinkedIn: linkedin.com/in/janedoe
- GitHub: github.com/janedoe

## Summary
Backend engineer with 4 years of experience building distributed systems in Go and Python. Focus on payments infrastructure, observability, and developer tooling. Comfortable owning services end-to-end from design to on-call.

## Experience

### Senior Backend Engineer — Acme Pay, Austin TX | Aug 2023–Present
- Cut p99 checkout latency 38% (820ms → 510ms) by replacing per-request DB lookups with a Redis-backed cache; rolled out to 100% traffic with zero incidents
- Led migration of 14 services from REST to gRPC, reducing inter-service payload size by 60% and standardizing auth across the platform
- Built an internal CLI used by 40+ engineers to scaffold new services; reduced new-service setup from 2 days to 30 minutes
- Mentor for 3 junior engineers; ran weekly design-review office hours
- Stack: Go, Postgres, Redis, gRPC, Kubernetes, Datadog

### Backend Engineer — Bluebird Health, Remote | Jun 2021–Jul 2023
- Designed HIPAA-compliant patient messaging service handling 2M messages/month; passed third-party security audit on first review
- Reduced background-job failure rate from 4.1% to 0.3% by adding idempotency keys and a Postgres-backed retry queue with exponential backoff
- Owned migration from monolith to 6 microservices; documented runbooks adopted as team standard
- Stack: Python, Django, Celery, Postgres, AWS (ECS, RDS, SQS)

### Software Engineering Intern — TexMart, Austin TX | May 2020–Aug 2020
- Built inventory-reconciliation tool that flagged $180K of mispriced SKUs in its first month
- Shipped a React admin dashboard used by store managers across 12 locations
- Stack: TypeScript, React, Node.js, MySQL

## Projects
- **opentrace** — Open-source distributed tracing helper for Go services; 1.2K GitHub stars, 8 contributors. Adopted by 2 known companies.
- **rentwatch.fyi** — Side project tracking rent prices across 4 cities; 6K monthly users. Stack: Next.js, Postgres, Playwright scrapers.

## Skills
- Languages: Go, Python, TypeScript, SQL
- Infrastructure: Kubernetes, Docker, Terraform, AWS (ECS, RDS, S3, SQS), GCP (basic)
- Databases: Postgres, Redis, DynamoDB
- Observability: Datadog, Prometheus, OpenTelemetry
- Other: gRPC, REST, GraphQL, CI/CD (GitHub Actions, ArgoCD)

## Education
- B.S. Computer Science, University of Texas at Austin, 2021
  - Honors: Dean's List 4 semesters
  - Relevant coursework: Distributed Systems, Operating Systems, Algorithms, Databases
