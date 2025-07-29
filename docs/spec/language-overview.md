# Language Overview

Experience Notation is a plain-text, structured language for modelling human experiences across systems, services and scenarios. It is designed to be both human-friendly and machine-parseable, offering a formal yet flexible way to define events, actions, personas, and contextual dynamics.

---

## Purpose

The language is built to:

- Capture the complexity of human experience in a consistent format
- Support simulation, analysis, testing, and design
- Enable collaboration across disciplines (UX, AI, policy, research)

Experience Notation bridges the gap between unstructured user stories and fully automated simulation or verification frameworks.

---

## Syntax Style

Experience Notation uses indentation-based, declarative syntax. It is designed to resemble readable outline-style prose:

```expn
Event: Login Attempt
  Step: Enter password
    User: Returning User
    Action: Types incorrect password
    UI-Element: Login form
    Conditional:
      IF: Password incorrect
      THEN: Show error
      ELSE: Proceed to dashboard
```

The syntax follows rules defined in an [EBNF grammar](ebnf.md).

---

## File Header

Each `.expn` file starts with a required header block:

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Multi-Agent Access Control
Journey-Description: Interaction flow involving multiple user roles
```

These fields define which syntax and grammar version is used and provide a description of the journey being modelled.

---

## Hierarchy and Structure

The language is structured hierarchically:

- A journey contains one or more **Events**
- Each **Event** contains one or more **Steps**, optionally **Personas**, **Disruptions**, **Parallel Events**, etc.
- Each **Step** contains properties like `User`, `Action`, `UI-Element`, and optionally `Conditional`, `Metrics`, and `Tags`

```expn
Event: Checkout
  Step: Add Item to Basket
    User: Shopper
    Action: Clicks add button
    UI-Element: Product Page
```

---

## Extensibility

Experience Notation allows:

- Inline and external `Persona` definitions
- Metadata via `Meta:` and `Tag:`
- Conditional branches (`IF`, `THEN`, `ELSE`)
- Cross-references via `Ref:` and `ID:`
- Support for context modelling (`Environmental-Factors`, `Disruption`, `Parallel-Events`)

---

## Validity and Compatibility

Experience Notation files are valid when:

- They conform to the [EBNF grammar](ebnf.md)
- They pass structural validation against the [JSON Schema](json-schema.md)

Tools and validators (in progress) will allow automated checking and transformation of `.expn` files.

---

Continue to [EBNF Grammar](ebnf.md) to see the formal structure.
