# JSON Schema Reference

This page provides a human-readable breakdown of the Experience Notation JSON Schema.

The schema defines the structure, types, and validation rules for `.expn` documents. It is used by tooling to ensure consistency, correctness, and compatibility across versions.

---

## Schema Metadata

- **$schema:** https://json-schema.org/draft/2020-12/schema
- **Title:** Experience Notation Document
- **Description:** A structured journey definition using the Experience Notation (expn) format, conforming to EBNF Version 1.1 and JSON Schema Draft 2020-12.
- **Version:** 1.1.0

---

## Top-Level Properties
### `ebnfVersion`
- Type: `string`
- Description: The version of the Experience Notation grammar this document conforms to (e.g., '1.1'). Corresponds to 'grammar_version' in EBNF.

### `syntaxVersion`
- Type: `string`
- Description: The version of the Experience Notation syntax used in this journey (e.g., '1.0'). Corresponds to 'Syntax-Version' in EBNF header.

### `journeyTitle`
- Type: `string`
- Description: A concise and descriptive name for the journey. Corresponds to 'Journey-Title' in EBNF header.

### `journeyDescription`
- Type: `string`
- Description: An overview of the journey's purpose, scope, and context. Corresponds to 'Journey-Description' in EBNF header.

### `events`
- Type: `array`
- Description: A list of events (major checkpoints or phases) in the journey. Corresponds to 'event' in EBNF.

### `personas`
- Type: `array`
- Description: A list of global persona definitions relevant across the journey. Corresponds to 'persona_global' in EBNF.

### `comments`
- Type: `array`
- Description: Top-level comments about the journey document. Corresponds to 'comment' in EBNF.

---
For complete validation rules, see the [Validation Guide](validation.md).
