# Module 6: Final Assessment

This final module gives you an opportunity to apply everything you’ve learned so far. You will model a complete experience using headers, events, steps, personas, conditionals, and annotations.

---

## Assessment Overview

In this task, you will model a user journey for an online ticket booking system. The user selects an event, provides personal details, chooses a seat, and completes payment. You will include conditional logic for success and failure, and at least one persona with metrics.

---

## Assessment Instructions

Create a valid `.expn` file that includes:

* Proper header fields
* At least **2 events** with **multiple steps** each
* A `Conditional:` block to handle alternate flows
* One global or inline `Persona:`
* Use of `UI-Element:`, `Meta:`, or `Tag:` where relevant

---

## Example Reference (Partial Only)

Use this as inspiration — your answer may vary in detail and structure.

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Ticket Booking
Journey-Description: A user purchases a ticket for a live event

Persona: Event Attendee
  Traits: { loyalty="returning" }
  Experience: Enjoys smooth browsing

Event: Browse Events
  Step: Search for events
    User: Event Attendee
    Action: Types query in search box
    UI-Element: Search Bar
    Tag: [search, navigation]

  Step: View event page
    User: Event Attendee
    Action: Reads description and selects event
    UI-Element: Event Details Page

Event: Book Ticket
  Step: Choose seat
    User: Event Attendee
    Action: Selects preferred seat from map
    UI-Element: Seating Chart

  Step: Submit payment
    User: Event Attendee
    Action: Enters payment details
    UI-Element: Payment Form
    Conditional:
      IF: payment fails
      THEN: display error message
      ELSE: show confirmation
```

---

## Review

Use this exercise to test your understanding of:

* Correct syntax and indentation
* Logical structuring of actions and decisions
* Modelling personas, experience, and outcomes

Review your `.expn` file by reading it aloud or validating it against the [EBNF grammar](../spec/ebnf.md).

You’ve completed the tutorial sequence. Congratulations!
