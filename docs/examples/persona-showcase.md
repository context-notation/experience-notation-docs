# Example: Advanced Personas

## Purpose

This example demonstrates how to represent multiple personas within a journey, including global and inline definitions. It shows how traits, metrics, and emotional responses can be modelled in Experience Notation.

## Features Demonstrated

* Global persona definitions
* Inline persona experiences within events
* Use of `Traits:`, `Metrics:`, `Experience:`, and `Adaptation:`

## Annotated Example

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Persona Showcase
Journey-Description: Demonstrates persona-driven modelling across multiple events

Persona: Knowledge Seeker
  Traits: { expertise="intermediate", patience="moderate" }
  Experience: Curious but cautious
  Metrics: { confidence=6 }

Event: Search for Help
  Step: Submit question
    User: Knowledge Seeker
    Action: Types query into search bar
    UI-Element: Support Portal

  Step: Read article
    User: Knowledge Seeker
    Action: Skims through documentation
    UI-Element: Help Article

  Persona: Knowledge Seeker
    Experience: Becomes slightly frustrated
    Adaptation: Skips to FAQ section
    Metrics: { patience=low }

Event: Contact Support
  Step: Open chat window
    User: Knowledge Seeker
    Action: Starts live chat with support agent
    UI-Element: Live Chat Interface

  Persona: Knowledge Seeker
    Experience: Feels reassured by human interaction
    Metrics: { confidence=8 }
```

## What You Can Learn

* How to structure reusable personas outside event blocks
* How to express internal states and changes in a step-by-step journey
* When to apply `Metrics:` and `Adaptation:` to reflect user shifts

Continue to [External Personas](external-personas.md) for linking users across systems or data sources.
