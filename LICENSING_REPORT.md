# Oracle JDK to Amazon Corretto Migration — Licensing Report

## Summary

| Item | Value |
|------|-------|
| Project Name | openmrs-core |
| Files Scanned | All `.java`, `pom.xml`, `Dockerfile`, `docker-compose*.yml`, `.sh`, `.properties`, `.yml`, `.yaml` files |
| Oracle API Imports Found | 0 |
| Issues Found & Fixed | 5 (Dockerfile ARGs + 3 CI workflow distribution fields) |
| Manual Review Items | 0 |

## Dependency Table

| File | Line | Oracle API | Replacement | Status |
|------|------|-----------|-------------|--------|
| N/A | — | No Oracle API imports detected | — | Pass |

## Licensing Cost Estimate

### Oracle Java SE Licensing Costs (Avoided)

| Employees | Rate | Monthly | Annual | 5-Year |
|-----------|------|---------|--------|--------|
| 500 | $15.00/emp/mo | $7,500 | $90,000 | $450,000 |
| 1,000 | $12.00/emp/mo | $12,000 | $144,000 | $720,000 |
| 5,000 | $10.50/emp/mo | $52,500 | $630,000 | $3,150,000 |
| 10,000 | $10.50/emp/mo* | $105,000 | $1,260,000 | $6,300,000 |

*10,000-employee rate extrapolated from highest published tier (3,000–9,999). Actual enterprise pricing negotiated with Oracle.

### Amazon Corretto Cost

**$0** — Amazon Corretto is a no-cost, multiplatform, production-ready distribution of OpenJDK with no licensing fees.

## Modified Files

| File | Change |
|------|--------|
| `Dockerfile` | Changed `DEV_JDK` ARG from `eclipse-temurin-21` to `amazoncorretto-21`; changed `RUNTIME_JDK` ARG from `jdk21-temurin` to `jdk21-corretto` |
| `.github/workflows/build.yaml` | Changed `distribution` from `temurin` to `corretto` |
| `.github/workflows/build-2.x.yaml` | Changed `distribution` from `adopt` to `corretto` |
| `.github/workflows/codeql-analysis.yml` | Changed `distribution` from `temurin` to `corretto` |

## Manual Review Items

None — no Oracle-specific API imports or unrecognized vendor patterns were found.

## Annotation-Processor Upgrades

Not applicable — no Lombok or annotation-processor compatibility issues detected.
