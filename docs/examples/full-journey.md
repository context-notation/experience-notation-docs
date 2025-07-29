# Example: Comprehensive CX Journey

## Purpose

This example brings together multiple features of Experience Notation into a single, complex customer support journey. It is ideal for illustrating long-form modelling with branching, personas, and contextual variables.

## Features Demonstrated

* Multi-event narrative with consistent flow
* Use of personas with traits and adaptations
* Conditional logic, tags, and metrics
* Contextual and environmental annotations

## Annotated Example

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Customer Support Lifecycle
Journey-Description: A user experiences an issue, seeks support, and receives resolution

Persona: Frustrated Customer
  Traits: { loyalty="medium", tech_savvy=true }
  Experience: Anxious due to unexpected service interruption
  Metrics: { mood="low" }

Event: Detect Problem
  Step: App crash
    User: Frustrated Customer
    Action: Attempts to open app, but it crashes
    UI-Element: Mobile App
    Disruption: App fails on launch
    Tag: [issue, crash]

Event: Seek Help
  Step: Try self-service
    User: Frustrated Customer
    Action: Searches FAQ section
    UI-Element: Help Centre

  Step: Start chat
    User: Frustrated Customer
    Action: Opens live chat for support
    UI-Element: Chat Widget
    Metrics: { patience=low }

Event: Troubleshooting
  Step: Submit ticket
    User: Frustrated Customer
    Action: Describes issue and attaches screenshot
    UI-Element: Support Form

  Step: Response received
    User: Support Agent
    Action: Reviews ticket and sends resolution steps
    UI-Element: Support Dashboard

  Persona: Frustrated Customer
    Adaptation: Calms down after receiving clear instructions
    Experience: Appreciates responsiveness
    Metrics: { mood="recovering" }

Event: Follow-up
  Step: Confirm resolution
    User: Frustrated Customer
    Action: Marks issue as resolved
    UI-Element: Ticket Portal
    Tag: [follow-up]

  Step: Feedback
    User: Frustrated Customer
    Action: Rates the experience
    UI-Element: Feedback Form
    Metrics: { satisfaction=8 }
```

## What You Can Learn

* How to combine multiple features in one cohesive `.expn` journey
* How to manage emotional and technical dimensions through personas
* How to model end-to-end lifecycle experiences

This concludes the curated examples library. Return to the [Examples Overview](index.md) to explore more scenarios or revisit previous examples.
