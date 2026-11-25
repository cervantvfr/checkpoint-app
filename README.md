# Checkpoint

Checkpoint is a clinic system for studying how its pieces interact. The architecture is in [docs/architecture.md](docs/architecture.md). The build order is in [docs/plan.md](docs/plan.md). The language is in [GLOSSARY-MAP.md](GLOSSARY-MAP.md).

## Implementation so far

Phase 1 is in place. The appointments service is a Java 21 Spring Boot 4.2.0 process. It exposes `GET /actuator/health` and has a context test. It does not store an Appointment yet. MongoDB, Keycloak, Kafka, and the other services are still ahead in the plan.

From `appointments/`:

```bash
mvn test
mvn spring-boot:run
```

Then:

```bash
curl -s http://localhost:8080/actuator/health
```

The context test passes. The curl is the remaining check for this phase: the body is `{"status":"UP"}`.
