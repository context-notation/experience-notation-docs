# Module 4: Advanced Personas

This module explores how to model advanced personas, including multiple personas, persona traits, and external persona referencing.

---

## Learning Outcomes

By the end of this module, you will be able to:

* Define multiple personas in a journey
* Link steps to external or global personas
* Express motivations, adaptations, and emotional reactions
* Model personas outside of events using global persona blocks

---

## Global vs Local Personas

Global personas are declared at the top level, outside any event. These are reusable across the file and can be referenced within steps or other personas.

```expn
Persona: Registered User
  Traits: { age_group="30s", familiarity="high" }
  Experience: Feels confident navigating interface
```

Local personas appear inside an event. They reflect an experience specific to a given context.

```expn
Event: Purchase Completion
  Step: Confirm order
    User: Buyer
    Action: Reviews order and confirms
    UI-Element: Checkout Page

  Persona: Buyer
    Experience: Relieved the process was quick
    Metrics: { satisfaction=9 }
```

---

## Scenario 1: Reusing External Persona

=== "Task"

    ```expn
    Declare a persona globally, then refer to them in multiple events.
    ```

=== "Answer"

    ```expn
    EBNF-Version: 1.1
    Syntax-Version: 1.0
    Journey-Title: Shopping Experience

    Persona: Frequent Shopper
      Traits: { loyalty_status="Gold" }
      Experience: Feels confident using the mobile app

    Event: Browse Products
      Step: Search catalogue
        User: Frequent Shopper
        Action: Enters keywords
        UI-Element: Search Bar

    Event: Add to Cart
      Step: Select product
        User: Frequent Shopper
        Action: Taps 'Add to Cart'
        UI-Element: Product Page
    ```

---

## Scenario 2: Adaptation and Emotional Response

=== "Task"

    ```expn
    Show how a persona changes as a result of an event.
    ```

=== "Answer"

    ```expn
    Event: Receive Negative Feedback
      Step: Read review
        User: Product Owner
        Action: Reads user complaint
        UI-Element: Admin Dashboard

      Persona: Product Owner
        Adaptation: Becomes more cautious about future releases
        Experience: Disappointed but reflective
        Metrics: { mood="low" }
    ```

---

## Best Practices

* Use global personas when referencing the same individual across multiple events
* Adaptations describe changes in attitude or strategy
* Combine `Experience:` and `Metrics:` to capture both subjective and quantifiable states

Next: [Module 5: Conditional Logic & Branching](conditional.md).
