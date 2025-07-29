# Example: External Personas

## Purpose

This example demonstrates how to reference personas defined in external sources. It is useful for distributed modelling where shared users or roles appear across multiple `.expn` files or systems.

## Features Demonstrated

* Use of `External-Source:` to link to external persona definitions
* Referencing remote personas within steps
* Maintaining consistency across modular experiences

## Annotated Example

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: External Persona Integration
Journey-Description: Uses an externally defined user role in the local journey

External-Source: https://example.com/personas/healthcare-personas.expn

Event: Access Medical Record
  Step: Open portal
    User: GP
    Action: Logs into patient management system
    UI-Element: Web Portal

  Step: View record
    User: GP
    Action: Opens recent patient file
    UI-Element: Patient Records Viewer
```

## What You Can Learn

* How to model journeys where users are defined elsewhere
* How to link `.expn` files with consistent referencing
* How to keep personas modular and reusable

Continue to [Contextual Factors](context.md) to see how external influences and disruptions can be represented in a journey.
