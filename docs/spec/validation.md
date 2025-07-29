# Validation Guide

This guide explains how to validate `.expn` files written in Experience Notation using the formal grammar and JSON Schema.

Validation ensures that your documents are syntactically correct and structurally compliant, improving reliability, consistency, and tool support.

---

## Tooling Status

> ⚠ Validation tools for Experience Notation are currently under development.
> Follow the [GitHub roadmap](https://github.com/context-notation/experience-notation) or join [Discussions](https://github.com/context-notation/experience-notation/discussions) for updates.

---

## 1. EBNF Grammar Validation

Experience Notation’s syntax is defined using an [EBNF grammar](ebnf.md), which must be interpreted via a parser.

While a reference implementation is in progress, early adopters can:

* Use parser generators such as:

  * [`lark`](https://github.com/lark-parser/lark) (Python)
  * [`nearley`](https://nearley.js.org/) (JavaScript)
  * [`ANTLR`](https://www.antlr.org/) (multi-language)
* Validate indentation and element structure manually

### Manual Validation Tips

* Use **two spaces** for indentation
* Ensure all required headers are present at the top
* Maintain correct ordering of elements like `Event`, `Step`, `Persona`
* Use consistent capitalisation (e.g. `User:` not `user:`)
* Follow a known valid example as a template

---

## 1. JSON Schema Validation

Experience Notation is validated using a [JSON Schema](json-schema.md), which defines:

* Required fields
* Data types (string, array, object)
* Enumerated values
* Format constraints

### Validate using CLI tools

```bash
npx ajv-cli validate -s experience-notation.schema.json -d my-journey.json
```

### Validate using Python

```python
import json
from jsonschema import validate

with open("experience-notation.schema.json") as f:
    schema = json.load(f)
with open("my-journey.json") as f:
    instance = json.load(f)

validate(instance=instance, schema=schema)
```

### JSON Schema in Editors

Most modern editors (e.g. VS Code) support `$schema` declarations:

```json
{
  "$schema": "https://schemas.experience-notation.com/experience-notation.schema@v1.1.0",
  "Journey-Title": "My Journey"
}
```

This enables:

* Autocompletion
* Inline validation
* Structural guidance