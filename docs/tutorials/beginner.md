# Module 2: Beginner Scenarios

This module introduces simple modelling patterns using Experience Notation. You’ll apply the core syntax learned in Module 1 to represent realistic experience flows.

---

## Learning Outcomes

By the end of this module, you will be able to:

* Represent multiple steps within a single event
* Use comments to explain decisions
* Practise consistent indentation and formatting
* Begin narrating user experience in a structured form

---

## Scenario 1: Contact Form

Imagine a website where a user fills in a contact form.

=== "Task"

    ```expn
    Model the following steps:
    - A user types a message
    - Clicks the send button
    - Sees a confirmation message
    ```

=== "Answer"

    ```expn
    EBNF-Version: 1.1
    Syntax-Version: 1.0
    Journey-Title: Contact Form Submission

    Event: Submit Message
      Step: Compose message
        User: Visitor
        Action: Types message into textarea
        UI-Element: Contact Form

      Step: Send message
        User: Visitor
        Action: Clicks send button
        UI-Element: Contact Form

      Step: Show confirmation
        User: Visitor
        Action: Sees confirmation message
        UI-Element: Web Page
    ```

---

## Scenario 2: Password Reset Flow

This exercise introduces a slightly longer sequence.

=== "Task"

    ```expn
    Model a password reset process:
    - User clicks "Forgot Password"
    - Receives an email
    - Clicks the reset link
    - Enters a new password
    ```

=== "Answer"

    ```expn
    EBNF-Version: 1.1
    Syntax-Version: 1.0
    Journey-Title: Password Reset
    Journey-Description: A user resets a forgotten password

    Event: Password Reset Request
      Step: Initiate reset
        User: Returning User
        Action: Clicks 'Forgot Password'
        UI-Element: Login Page

      Step: Receive email
        User: Returning User
        Action: Checks inbox for password reset
        UI-Element: Email Client

      Step: Follow reset link
        User: Returning User
        Action: Clicks password reset link
        UI-Element: Email Client

      Step: Enter new password
        User: Returning User
        Action: Sets new password
        UI-Element: Reset Form
    ```

---

## Best Practices

* Keep steps concise and action-driven
* Use comments (`#`) to explain specific behaviours if needed
* Maintain consistent user naming throughout the journey

---

Next up: [Module 3: Intermediate Modelling](intermediate.md), where you’ll explore personas, nested fields, and contextual complexity.
