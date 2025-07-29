# Core Concepts

Experience Notation is built around composable, hierarchical elements that describe human journeys in context.

This section introduces the core syntax and semantics of the language.

---

## Overview of Key Elements

| Element             | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `Event:`            | A major checkpoint or segment in the journey                                |
| `Step:`             | A specific action, interaction, or system response                          |
| `Persona:`          | A user or stakeholder involved in the journey (inline or external)          |
| `User:`             | The actor performing the step                                               |
| `Action:`           | What the user does (or attempts to do)                                      |
| `UI-Element:`       | The interface or channel involved                                            |
| `Conditional:`      | Decision logic using `IF... THEN... [ELSE...]`                              |
| `Disruption:`       | A failure, interruption, or breakdown                                        |
| `Environmental-Factors:` | Broader contextual influences                                          |
| `Parallel-Events:`  | Concurrent experiences occurring alongside the main flow                    |
| `Metrics:`          | Numeric, boolean, or textual indicators attached to personas or steps       |
| `Meta:`             | Arbitrary metadata in `key=value` format                                    |
| `Tag:`              | Categorical labels used for filtering or analysis                           |
| `Ref:`              | Internal links to previously defined elements using unique IDs              |

---

## File Header

Each `.expn` file begins with required headers:

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Booking Flow with Delay
Journey-Description: User journey through online ticket booking with service outage
```
These headers define the file’s syntax version and purpose.

---

## Structure and Indentation

Experience Notation uses indentation for structure. For example:

```expn
Event: Service Outage
  ID: EVT-003
  Step: Try to Access Account
    User: Returning Customer
    Action: Attempts to log in
    UI-Element: Login Form
    Conditional:
      IF: Password incorrect
      THEN: Display error
      ELSE: Proceed to dashboard
  Disruption: System latency causes login delay
```

* Event-level indentation: 2 spaces
* Step-level and persona-level: 4 spaces
* Nested logic and blocks: 6+ spaces as needed

---

## Reuse and Modularity

Experience Notation supports modular thinking:

* Use `ID:` to name key elements
* Use `Ref:` to point to them later
* Global `Personas:` can be declared once and reused across the document
* External personas can be linked via `External-Source:`

---

## Best Practices

* Use comments (`#`) to annotate files during drafting
* Validate files against the JSON Schema
* Keep indentation consistent 
* Use metrics and metadata to enable analysis
* Design with real-world behaviour and breakdowns in mind

---

Continue to [Quick Example](example.md) for a complete working journey.