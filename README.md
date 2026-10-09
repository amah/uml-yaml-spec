# UML YAML Specification

Draft, implementation-independent YAML serialization for a subset of UML 2.5.1.

This project is not an OMG standard. It contains schemas, normative documentation, examples and conformance fixtures, not implementation code.

## Status

Initial draft v0.1.0. The specification is evolving and does not yet claim XMI round-trip compatibility.

## Principles

- Stable element IDs and explicit references
- UML metaclasses, profiles, stereotypes, and tagged values
- YAML 1.2 and JSON Schema Draft 2020-12
- Semantic model separated from diagram layout
- Independent of DDD, microservices, and programming languages

See `specification/` and `schemas/v0.1/` for details.
