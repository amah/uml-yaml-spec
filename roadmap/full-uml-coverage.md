# Roadmap: UML 2.5.1 semantic coverage

Status: **planned**. The existing v0.1 schema is a limited subset, not full UML.

## Definition of complete coverage

For each normative UML metaclass, enumeration, and data type: document its identity, generalizations, structural features, references, multiplicities, derived and union semantics, ownership, and constraints. Capture semantic equivalence and any serialization-specific differences. Track profiles and stereotype applications independently.

Diagram interchange (DI), notation, and XMI round-trip equivalence are distinct deliverables and must not be conflated with semantic UML coverage.

## Phases

1. Inventory official UML metamodel artifacts; assign stable metaclass identifiers and traceability links.
2. Define foundational elements: Element, NamedElement, Namespace, PackageableElement, Type, TypedElement, Relationship, DirectedRelationship, MultiplicityElement, ValueSpecification, Constraint.
3. Complete structural modeling: classifiers, features, associations, generalizations, packages, components, composite structures, templates.
4. Complete behavior: Behavior, Activities, Actions, StateMachines, Events, Triggers.
5. Complete interactions, use cases, deployments, and information flows.
6. Complete profiles, stereotypes, extensions, and standard UML profile.
7. Add normative constraint catalog, semantic validation expectations, and XMI mapping/conformance.
8. Optionally specify diagram interchange and notation in a separate module.

## Acceptance criteria

- Every official metaclass and enum accounted for in a machine-readable coverage manifest.
- Every structural feature mapped with type, cardinality, ownership, and derivation status.
- Each normative constraint documented and covered by a positive/negative conformance fixture where representable.
- Automated cross-checks performed in an **external** validation/toolchain project (this repository remains code-free).
- Explicit unsupported/deferred features; no unqualified claims of full UML or lossless XMI until verified.

## Versioning

Retain `v0.1` unchanged. Develop expanded schemas under `schemas/v0.2/` and mark them draft until conformance requirements are met.
