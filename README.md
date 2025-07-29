# Experience Notation

![Open DSL](https://img.shields.io/badge/DSL-open-4c1.svg)
![Grammar EBNF](https://img.shields.io/badge/grammar-EBNF-informational.svg)
![Apache 2.0](https://img.shields.io/badge/licence-Apache%202.0-blue.svg)
![Pygments Lexer](https://img.shields.io/badge/syntax%20highlighting-pygments-orange.svg)

---

**Experience Notation** is a domain-specific language (DSL) for modelling human experience in a structured, machine-readable format. 

Originally developed as part of **[Demoscope.ai](https://demoscope.ai)**, a commercial platform for LLM-powered synthetic user feedback and behavioural insights, Experience Notation has grown into a general-purpose modelling language for complex, human-centred experiences.

It is designed to support design research, behavioural prototyping, AI simulation, and service modelling workflows. It enables researchers, designers, policymakers and technologists to represent user journeys, decisions and contextual factors from a human-centred perspective. The language supports personas, actions, branching logic, environmental influences, disruptions, behavioural metrics and more.

Experience Notation is open and extensible.  
[View on GitHub](https://github.com/context-notation/experience-notation)

---

## Key Features

* **Human- and machine-readable**: Write in plain text that both people and systems can understand
* **Structured grammar**: Validated by an EBNF specification for syntax correctness and tooling
* **Modular elements**: Use `Event`, `Step`, `Persona`, `Conditional`, `Metric`, `Tag`, `Ref`, `Meta`, and `Disruption` blocks to model complexity
* **Support for branching logic**: Model decisions and outcomes using `IF`, `THEN`, and `ELSE` constructs
* **Persona modelling**: Define users inline or externally using `External-Source` and enrich them with experience, interaction, and adaptation attributes
* **Environmental context**: Capture contextual factors and real-world conditions using `Environmental-Factors` and `Disruption`
* **Metadata and tagging**: Attach key-value pairs and identifiers for filtering, categorisation, and semantic structure
* **Parallel events and referencing**: Model concurrent paths using `Parallel-Events` and interlink steps and events via `Ref`

---

## Where Experience Notation Could Be Applied

Designed to address real-world complexity, Experience Notation helps researchers and technologists model and analyse human journeys with clarity and structure. Below are domains where it shows early promise.


| Domain | Application |
|--------|-------------|
| **AI Safety** | Model coordination failures, edge-case decisions and value conflicts to support safe deployment of LLMs |
| **Government** | Simulate public service interactions, emergency response flows and population-wide accessibility impacts |
| **Product Design** | Map user journeys to identify service friction, accessibility gaps and opportunities for inclusive improvement |
| **Healthcare** | Model goal-driven journeys involving behavioural triggers, disruptions and personal adaptation over time |

---

## Who Is It For?

- AI safety researchers simulating agent behaviour
- Designers mapping inclusive service experiences
- Policy teams evaluating accessibility and impact
- Developers building human-aware systems

Whether you are modelling risk, prototyping services or benchmarking language models, Experience Notation offers a structured and interpretable approach to reasoning about experience.

---

> **Join our community** to shape the future of human-centred design and AI  
> [GitHub Discussions](https://github.com/context-notation/experience-notation/discussions)

___

## Support & Collaboration

Experience Notation was authored by **Nikolaos Maniatis** and is maintained by **The Cato Bot Company Limited** as part of the [Context Notation](https://context-notation.com) initiative.


For questions about:
- Using Experience Notation in your projects
- Contributing to development
- Research collaborations  
- Commercial support options

Feel free to reach out:

📧 [hello@context-notation.com](mailto:hello@context-notation.com)  
💬 [GitHub Discussions](https://github.com/context-notation/experience-notation/discussions)  
🌐 [context-notation.com](https://context-notation.com)