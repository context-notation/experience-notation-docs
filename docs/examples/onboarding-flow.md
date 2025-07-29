# Example: Simple Onboarding

## Purpose

This example demonstrates a basic onboarding flow, where a new user signs up and logs into a platform. It shows how to structure events and steps with minimal logic or metadata.

## Features Demonstrated

* Sequential events and steps
* Clear use of `User:`, `Action:`, and `UI-Element:`
* Basic journey structure and indentation

## Annotated Example

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Onboarding Flow
Journey-Description: A user signs up and logs in for the first time

Event: User Registration
  Step: Fill out form
    User: New Visitor
    Action: Enters name, email, and password
    UI-Element: Registration Form

  Step: Submit registration
    User: New Visitor
    Action: Clicks "Register"
    UI-Element: Registration Form

Event: Email Confirmation
  Step: Confirm email
    User: New Visitor
    Action: Clicks link in confirmation email
    UI-Element: Email Client

Event: First Login
  Step: Enter credentials
    User: New User
    Action: Types email and password
    UI-Element: Login Form

  Step: Access dashboard
    User: New User
    Action: Sees welcome screen
    UI-Element: Dashboard
```

## What You Can Learn

* How to model a multi-step user journey using the basic syntax
* How to distinguish between events and steps
* Naming and structuring user actions in a linear flow

Continue to [User Decision Flow](decision-flow.md) to explore conditional logic.
