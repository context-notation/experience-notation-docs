# What Is Experience Notation?

**Experience Notation** is a domain-specific language (DSL) for describing complex human journeys, decisions, and disruptions using structured text. It is designed to be both human-readable and machine-parseable, enabling deeper understanding, simulation, and integration of real-world experience into digital systems.

It empowers researchers, designers, technologists, and policymakers to represent human behaviour with clarity, context, and structure.

---

## Why Experience Notation Exists

Modern services and systems are often complex, fragmented, and unpredictable. Traditional tools for mapping experience are often:

- Visually rich but semantically thin
- Inconsistent in format
- Hard to validate or simulate
- Disconnected from engineering and data workflows

Experience Notation solves these problems by providing:

- A **grammar-based, validated structure** for defining experiences
- **Shared vocabulary** across roles and disciplines
- A format that is **portable, versionable, and extensible**
- Compatibility with automation, simulation, and AI workflows

---

## What Makes It Different?

| Feature                         | Traditional Journey Maps       | Experience Notation                      |
|----------------------------------|-------------------------------|------------------------------------------|
| Visual design tool              | Yes                           | Optional (can be visualised)             |
| Human-readable                  | Yes                           | Yes                                      |
| Machine-readable                | Rarely                        | Yes (validated by grammar and schema)    |
| Branching and logic             | No                            | Yes (`IF`, `THEN`, `ELSE`)               |
| Structured personas             | No                            | Yes (`Persona`, `Metrics`, `Adaptation`) |
| Simulatable and testable        | Rare                          | Yes                                      |
| Version-controlled (text-based) | No                            | Yes (`.expn` format)                    |

---

## Use Cases Across Domains

| Sector              | Applications                                                   |
|---------------------|----------------------------------------------------------------|
| **Design & UX**     | Structured journey maps, service blueprints, inclusive design  |
| **Public Sector**   | Modelling citizen experiences, accessibility testing           |
| **Policy & Research**| Translating qualitative data into scenario models              |
| **Product Teams**   | Edge case documentation, QA, design-to-dev handoffs            |
| **AI & Simulation** | Ethical testing, scenario training, persona modelling          |
| **Education**       | Teaching systems thinking, behavioural modelling               |

---

## Experience Notation in Practice

A typical `.expn` file might include:

- Structured **events** and **steps**
- Personas and their **experiences**
- Metrics like satisfaction or confidence
- Conditional logic to explore "what if" flows
- Context like **disruption**, **environment**, and **parallel events**

You can write .expn files by hand in any text editor, or prompt a large language model (LLM) to generate them from natural language descriptions. Once written, you can validate the documents using the Experience Notation grammar and the official tools and schema (coming soon).


---

## Next Step

Now that you know what Experience Notation is, continue to:

👉 [Core Concepts](core-concepts.md) to learn the building blocks.
