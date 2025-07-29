# Quick Example

Here is a minimal Experience Notation document:

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Simple User Onboarding
Journey-Description: A basic journey for new user registration and login.

Event: Account Creation
  ID: EVT-001
  Step: User Registration
    User: New User
    Action: Fills out form
    UI-Element: Registration Page
  Step: Email Verification
    User: New User
    Action: Clicks email link
    UI-Element: Email Client
  Persona: Referenced Persona
    External-Source: https://example.com/personas/user-v1.json

Event: First Login
  ID: EVT-002
  Step: Initial Login
    User: Registered User
    Action: Logs in
    UI-Element: Login Page
  Persona: Excited New User
    Experience: Feels welcomed and confident
    Metrics: {"satisfaction": 8, "confidence": "High"}
```

---

This shows:

- Two events with clear IDs
- Steps with associated users, actions, and UI context
- Both external and inline personas
- Use of metrics to capture user experience

You can expand this with conditionals, disruptions, metadata, and more.
