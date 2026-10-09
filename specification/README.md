# UML YAML v0.1 — draft specification

This repository proposes a YAML 1.2 serialization for a **subset** of UML 2.5.1. It is not an OMG standard.

## Document envelope

A document MUST contain `apiVersion: uml-yaml.org/v0.1`, `kind: uml:Model`, `metadata` (with stable `id` and `name`), and `packagedElements`.

Each packaged element has `id`, `type`, and `name`. The supported types are Package, Class, Interface, Component, Enumeration, Association, Profile, and Stereotype, with the `uml:` prefix.

## Identity and references

IDs MUST be unique within the document and SHOULD be stable across renames. A reference is a nonempty string and MUST resolve to an element in the document, an explicitly imported model (future work), or a recognized UML primitive/metaclass reference. Names are not identities.

## UML profiles

A `uml:Profile` owns `uml:Stereotype` elements. A stereotype declares `extensions` with `metaclassRef` and typed `tagDefinitions`. A model or package declares `appliedProfiles`. Model elements carry `stereotypeApplications` with `stereotypeRef` and tagged `values`. A validator MUST check profile scope, metaclass compatibility, tag names, types, and multiplicities. Stereotype generalizations use `generalizations`.

## Semantics beyond JSON Schema

A semantic validator MUST detect duplicate IDs, dangling references, inheritance cycles, invalid multiplicities, association ends that do not resolve to classifiers, and invalid stereotype applications. JSON Schema validates document shape only.

## Deliberate limitations

This draft is not a lossless serialization of the complete UML metamodel. Behavioral diagrams, XMI round-tripping, imports, constraints, full association ownership semantics, and detailed UML metaclass inheritance are deferred. Diagram layout is outside the semantic document.

## Versioning

The `apiVersion` identifies the serialization contract. Breaking schema or semantic changes require a new language version.
