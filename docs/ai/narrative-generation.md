# From Journey to Narrative

## Overview

Experience Notation provides a rich, structured representation of user journeys. With large language models (LLMs), you can convert these formal models into engaging narratives, first-person stories, or UX case studies.

This guide explains how to prompt LLMs to generate natural language outputs based on `.expn` journeys, maintaining fidelity to personas, context, and emotional tone.

---

## Why Generate Narratives from `.expn`?

* Translates structured design into human-readable form
* Useful for stakeholders, usability reporting, or storytelling
* Captures the lived experience from the perspective of defined personas
* Helps explore emotional and behavioural impact

---

## Prompt Strategy: Convert Journey to First-Person Story

Provide the LLM with a valid Experience Notation file and ask it to retell the journey from the perspective of one of the defined personas.

### Example Prompt: Journey to Narrative

```plaintext
Below is an Experience Notation journey. Write a short first-person story from the point of view of the persona involved in the steps.

Experience Notation:

Persona: Returning Customer
  Traits: { loyalty=medium, patience=low }
  Experience: Wants a quick resolution after recent issues

Event: Reopen Account
  Step: Visit site
    User: Returning Customer
    Action: Opens the homepage
    UI-Element: Home

  Step: Enter credentials
    User: Returning Customer
    Action: Types username and password
    UI-Element: Login Form

  Step: Locked out
    User: Returning Customer
    Action: Encounters account lock message
    UI-Element: Modal Dialog

  Step: Contact support
    User: Returning Customer
    Action: Sends support request
    UI-Element: Contact Form

  Step: Receives email
    User: Returning Customer
    Action: Gets response with unlock link
    UI-Element: Email
```

### Expected Output

```plaintext
"I just wanted to check my order status, but when I logged in, I was locked out. The warning popped up without explanation. I felt frustrated — I’ve had issues before. I used the support form, hoping someone would respond quickly. Thankfully, an email arrived not long after with a link. At least this time it worked."
```

---

## Tips

* Include only the relevant persona’s actions and traits
* Maintain first-person voice and align tone with `Experience:` and `Metrics:` fields
* Remove technical syntax from the prompt (e.g., block headers) if needed for more natural phrasing
* Encourage storytelling that maps step-by-step onto the journey

---

## Extended Use: Generate Summaries for Stakeholders

In addition to stories, you can prompt the model to generate:

* Executive summaries of the journey
* Persona-specific walkthroughs
* Narrative UX case studies

---

## Prompt Example: Generate an Empathy-Focused Summary

```plaintext
Here is an `.expn` journey. Summarise the user's experience with empathy, highlighting their emotional reactions at each step.

[Insert Experience Notation content here]
```

---

This concludes the AI & LLM Integration section. Return to the [Tutorials](../tutorials/syntax-primer.md) to explore more foundational modelling examples.
