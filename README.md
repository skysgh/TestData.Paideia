# TestData.Paideia

Synthetic **education overlay** on top of `TestData.Base`. Schools, roles, enrolments, learner profiles, learning profiles. Knows nothing about humans-in-general — it points to Personas authored in `TestData.Base`.

> **Status**: bootstrap scaffold. Education ReferenceData skeletons in place. One anchor School with worked Staff + Enrolment + LearnerProfile + LearningProfile examples. Generator script not yet implemented.
>
> **Authoritative architecture**: `DOCUMENTATION/04.Architecture/03.Patterns/TestData/ARCHITECTURE-TESTDATA.md`
> **Authoritative implementation**: `DOCUMENTATION/06.Development/TestData/IMPLEMENTATION-TESTDATA.md`
> **Governing decision**: ADR-017-TESTDATA-SYNTHETIC-POPULATION

## Hard rules

- **Dev / test / demo non-production only.** Never seeded into prod.
- **No real schools, no real students.** All entries are synthetic.
- **YAML only.**
- **Every persona reference points to a Persona in `TestData.Base`** by `{alias}.P{n}`, never by GUID.
- **No human re-definition.** This repo never authors Persons or Personas; it enrols existing ones.

## Layout

```
ReferenceData/
Schools/
Enrolments/{school-slug}/{personaRef}.yml
LearnerProfiles/{personaRef}.yml
LearningProfiles/{personaRef}.yml
StaffAssignments/{school-slug}.yml
_Generator/
```

## Why 42 schools

The target count of 42 schools is deliberate: it gives two full pages of 20 + 2 of overhang, exercising the partial-final-page case in every UX list, every OData `$top/$skip` round-trip, and every report. Pagination off-by-one errors that 40/50/100 silently hide will surface against 42. The Hitchhiker's Guide resemblance is incidental.

## Naming

The repository is named **Paideia** (Greek παιδεία — formation, education) to align with the existing `BASE.Modules.Paideia` LM.
