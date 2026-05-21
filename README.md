# TestData.Paideira

Education overlay (learners, schools, roles, assessments) on top of TestData.Base.

> Status: bootstrap commit. Schema, ReferenceData, and generator scripts land in subsequent commits.
> Authoritative architecture: see \DOCUMENTATION/04.Architecture/03.Patterns/TestData/ARCHITECTURE-TESTDATA.md\
> Authoritative implementation: see \DOCUMENTATION/06.Development/TestData/IMPLEMENTATION-TESTDATA.md\
> Governing decision: see ADR-TESTDATA-SYNTHETIC-POPULATION.

## Constraints
- Dev / test / demo non-production only. Never seeded into prod.
- No real persons. Curated name pools partitioned by culture.
- YAML only. No JSON. No SQL.
- Cross-file references use stable human-memorable Alias keys (e.g. \cat-hat-roof\), not GUIDs.
- Personas are identified as \{PersonAlias}.P{n}\.