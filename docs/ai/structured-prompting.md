# Generating Experience Notation Journeys with LLMs

## Overview

Structured prompting refers to crafting LLM prompts that guide the model to return predictable, well-formed outputs. Experience Notation is particularly suited for this purpose thanks to its consistent block syntax, defined EBNF grammar, and human-readability.

This guide demonstrates how to prompt large language models to produce `.expn` journeys directly.

---

## Why Use Experience Notation in Prompts?

* Encourages models to produce structured, multi-step outputs
* Helps LLMs represent flows, personas, and decision logic
* Reduces the ambiguity of natural language-only tasks
* Can be validated against the [EBNF grammar](../spec/ebnf.md)

---

## Prompt Strategy: Providing Structure

LLMs respond more accurately when the output format is suggested explicitly.

Including the [full EBNF grammar](../spec/ebnf.md) or a simplified form of the Experience Notation structure can:

* Reduce hallucinated fields
* Improve field ordering and indentation
* Help the model understand block hierarchy

### Option A: Full EBNF Embedding

💡 **Recommended when tokens are not an issue.**
Include the complete EBNF specification in the prompt for maximum structural fidelity.

```plaintext
You are a UX modeller. Generate an Experience Notation journey from the scenario below.
Use the EBNF grammar that follows to guide the structure.

Scenario:
A new user signs up, verifies their email, and logs into the platform.

---
EBNF Specification:
[Insert full EBNF grammar here]
```

### Option B: Minimal Format Hint

Use a format hint like this at the end of your prompt:

```plaintext
Each step follows this structure:
Step:
  User: [persona name]
  Action: [what the user does]
  UI-Element: [interface they interact with]
  Conditional:
    IF: [condition]
    THEN: [result]
    ELSE: [alternative result]
```

---

## Prompt Example: Zero-Shot

```plaintext
You are a UX modeller. Describe the following onboarding flow using Experience Notation:

Scenario:
A user visits a website, signs up with email, confirms via email link, and logs in.

Return the output in `.expn` format. Use clear indentation and syntax blocks.
```

### Sample Output

```plaintext
Journey-Title: Basic Onboarding
Journey-Description: A user signs up and logs into the platform

Event: Sign Up
  Step: Enter details
    User: New Visitor
    Action: Fills out name and email
    UI-Element: Signup Form

  Step: Submit form
    User: New Visitor
    Action: Clicks "Register"
    UI-Element: Signup Form
```

---

## Prompt Example: Few-Shot Completion

```plaintext
Here’s a partial Experience Notation journey. Complete the next event using the same format.

EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Support Ticket

Event: Submit Issue
  Step: Describe problem
    User: Frustrated Customer
    Action: Types issue into support form
    UI-Element: Contact Page

[Continue with next event...]
```

---

## Tips

* Always anchor to `EBNF-Version: 1.1` and `Syntax-Version: 1.0` if possible
* Use delimiters or triple backticks to frame outputs
* Be specific about persona names and UI interactions
* When tokens allow, embed the full EBNF grammar
* Start with a minimal version for lightweight prompting, then scale

---

Continue to [Roleplaying Personas](roleplay.md) to explore how Experience Notation enables agent simulation.
