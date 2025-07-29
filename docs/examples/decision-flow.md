# Example: User Decision Flow

## Purpose

This example demonstrates the use of conditional logic in a decision-making journey. It showcases how to structure `Conditional:` blocks using `IF`, `THEN`, and `ELSE` clauses to capture branching outcomes.

## Features Demonstrated

* Use of `Conditional:` inside steps
* Modelling different outcomes for success and failure
* Clear structuring of alternate flows

## Annotated Example

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Decision Flow
Journey-Description: A user completes an action that can succeed or fail

Event: Submit Application
  Step: Complete form
    User: Applicant
    Action: Enters required details
    UI-Element: Application Form

  Step: Submit form
    User: Applicant
    Action: Clicks "Submit"
    UI-Element: Application Form
    Conditional:
      IF: required fields are missing
      THEN: show validation error
      ELSE: proceed to confirmation

Event: Confirmation
  Step: Show success screen
    User: Applicant
    Action: Sees confirmation message
    UI-Element: Web Page
```

## What You Can Learn

* How to embed conditionals within steps
* How to model different user outcomes clearly and readably
* Where to place conditional logic in a flow

Continue to [Advanced Personas](persona-showcase.md) for richer modelling of individuals and their experiences.
