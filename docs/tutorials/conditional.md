# Module 5: Conditional Logic & Branching

This module focuses on how to represent branching logic using the `Conditional:` block in Experience Notation. You’ll learn how to model decision points, alternate paths, and structured IF–THEN–ELSE expressions.

---

## Learning Outcomes

By the end of this module, you will be able to:

* Use the `Conditional:` block within steps
* Distinguish between IF, THEN, and ELSE
* Apply conditional logic to model both positive and negative paths
* Keep logic clear and readable using consistent formatting

---

## Basic Conditional Structure

```expn
Conditional:
  IF: user input is invalid
  THEN: display error message
  ELSE: proceed to next step
```

A `Conditional:` block must:

* Be indented inside a `Step:`
* Include at least `IF:` and `THEN:` lines
* Optionally include `ELSE:`

---

## Scenario 1: Form Validation

=== "Task"

    ```expn
    Model a form submission step with conditional feedback based on input.
    ```

=== "Answer"

    ```expn
    Event: Submit Form
      Step: Enter email address
        User: Guest
        Action: Clicks submit button
        UI-Element: Signup Form
        Conditional:
          IF: email field is empty
          THEN: display validation error
          ELSE: show success message
    ```

---

## Scenario 2: Payment Status

=== "Task"

    ```expn
    Represent a conditional flow for a payment process where the outcome depends on success.
    ```

=== "Answer"

    ```expn
    Event: Process Payment
      Step: Submit card details
        User: Buyer
        Action: Clicks "Pay Now"
        UI-Element: Checkout Form
        Conditional:
          IF: payment fails
          THEN: display failure message
          ELSE: show confirmation screen
    ```

---

## Best Practices

* Keep conditions readable and domain-relevant
* Avoid overly complex or deeply nested conditionals
* Use `THEN:` and `ELSE:` outcomes that are clear and actionable

---

Next: [Module 6: Final Assessment](final-assessment.md).
