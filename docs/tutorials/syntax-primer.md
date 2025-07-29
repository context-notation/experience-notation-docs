# Module 1: Syntax Primer

This module introduces the core syntax of Experience Notation. You’ll learn how to structure basic experience flows using the indentation-based format defined by the [EBNF grammar](../spec/ebnf.md).

---

## Learning Outcomes

By the end of this module, you will be able to:

* Structure a valid `.expn` file with headers
* Define `Event` and `Step` blocks
* Use `User`, `Action`, and `UI-Element` elements correctly
* Understand the importance of indentation and consistency

---

## File Header

All `.expn` files begin with a header that defines versioning and context:

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Basic Login Flow
Journey-Description: A simple login experience for returning users
```

These fields are required and must appear at the top of every file.

---

## Events and Steps

The core structure of Experience Notation is built from `Event:` and `Step:` blocks. Each event represents a significant moment in the journey. Steps are actions that occur within that event.

```expn
Event: Login Attempt
  Step: Enter credentials
    User: Returning User
    Action: Types in username and password
    UI-Element: Login Form
```

### Indentation Rules

* Use **2 spaces** for each level of nesting
* Keywords must be capitalised exactly as defined (`Step:`, not `step:`)
* Do not use tabs

---

## Descriptive Fields

Each step typically contains the following:

* `User:` — Who is acting in this step
* `Action:` — What the user does
* `UI-Element:` — The interface or medium used

```expn
Step: Confirm email
  User: New Registrant
  Action: Clicks verification link
  UI-Element: Email Client
```

These descriptive fields help capture the user experience in a structured way.

---

## Comments

You may use comments in your `.expn` file for annotation:

```expn
# This step represents the point of highest drop-off
Step: Provide payment details
  User: Guest
  Action: Enters credit card info
  UI-Element: Payment Form
```

Comments start with `#` and are ignored by any parser.

---

## Exercise

=== "Task"

    ```expn
    Create a simple `.expn` file that includes:
    - A header
    - One event
    - Two steps
    - At least one UI element
    - A comment
    ```

=== "Answer"

    ```expn
    EBNF-Version: 1.1
    Syntax-Version: 1.0
      Journey-Title: Newsletter Signup
    Journey-Description: A user subscribes to updates via a form

    Event: Signup
      Step: Enter email address
        User: Visitor
        Action: Types email in field
        UI-Element: Signup Form

      # Optional follow-up
      Step: Confirm email receipt
        User: Visitor
        Action: Clicks confirmation link
        UI-Element: Email Client
    ```

---

Continue to [Module 2: Beginner Scenarios](beginner.md) to practise simple journeys using these syntax rules.
