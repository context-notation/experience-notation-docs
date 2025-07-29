# Module 3: Intermediate Modelling

This module introduces more advanced constructs including nested fields, conditional logic, and the use of `Persona:` blocks to represent perspectives, motivations, and experiences.

---

## Learning Outcomes

By the end of this module, you will be able to:

* Model `Persona:` blocks within or outside events
* Use `Conditional:` logic blocks for branching
* Add `Metrics:` and `Meta:` fields
* Structure more complex event flows

---

## Scenario 1: Persona within an Event

=== "Task"

    ```expn
    Model a login journey that includes a persona who expresses a reaction after successful login.
    ```

=== "Answer"

    ```expn
    EBNF-Version: 1.1
    Syntax-Version: 1.0
    Journey-Title: Logged-In Persona Feedback

    Event: Login Success
      Step: Login attempt
        User: Returning User
        Action: Enters correct credentials
        UI-Element: Login Form

      Persona: Returning User
        Experience: Feels confident after successful login
        Metrics: { confidence=high }
    ```

---

## Scenario 2: Conditional Logic

=== "Task"

    ```expn
    Create an event with a conditional outcome:
    - User submits form
    - IF required fields are empty, show error
    - ELSE submit the form
    ```

=== "Answer"

    ```expn
    Event: Form Submission
      Step: Submit details
        User: Guest
        Action: Clicks submit button
        UI-Element: Registration Form
        Conditional:
          IF: Required fields are empty
          THEN: Show error message
          ELSE: Proceed with submission 
    ```

---

## Scenario 3: Adding Metadata

=== "Task"

    ```expn
    Use `Meta:` and `Tag:` fields to annotate steps for clarity.
    ```

=== "Answer"

    ```expn
    Event: Newsletter Signup
      Step: Fill email field
        User: Visitor
        Action: Enters email address
        UI-Element: Signup Form
        Meta: { source="homepage" }
        Tag: [conversion, email]
    ```

---

## Best Practices

* Use personas to reflect internal states, feedback, or goals
* Apply `Metrics:` to quantify subjective experiences
* Reserve `Conditional:` blocks for simple branching logic (do not nest them recursively)

Next: [Module 4: Advanced Personas](advanced-personas.md), where we explore external personas and cross-referenced experiences.
