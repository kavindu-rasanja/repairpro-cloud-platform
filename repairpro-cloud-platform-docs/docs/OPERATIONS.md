# Operations and Support

## Monitoring

Track:
- cloud API availability and latency;
- authentication failures and suspicious access;
- sync queue depth, age and rejection rate;
- database errors and quota usage;
- SMS submission and delivery failure rate;
- desktop crash rate and update failures;
- backup completion and restore-test status.

## Support severity

| Severity | Example | Response |
|---|---|---|
| Critical | Cross-tenant data exposure, widespread data loss | Contain immediately; incident process |
| High | Multiple branches unable to operate | Prioritize service restoration |
| Medium | Major workflow degraded with workaround | Schedule urgent fix |
| Low | Cosmetic issue or minor usability defect | Normal backlog |

Response targets are `TBD` and must be published only after support capacity is established.

## Incident record

Use `docs/templates/INCIDENT_TEMPLATE.md`. Preserve relevant evidence, avoid copying customer personal data into issue trackers, and document corrective actions.
