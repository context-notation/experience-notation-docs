# Roleplaying Personas with LLMs

## Overview

Experience Notation enables LLMs to participate in structured roleplaying by anchoring behaviour, traits, and emotional context within a formal model. This guide focuses on prompting LLMs to **act out roles inside journeys**, using complete `.expn` files that include both `Persona:` blocks and related `Event:` steps.

Unlike basic persona prompts, this approach places characters inside a sequence of experiences — making their reactions, decisions, and expressions more grounded and meaningful.

---

## Why Roleplay Inside `.expn`?

* Adds believability and depth to user modelling
* Supports simulations, usability walkthroughs, and agent testing
* Anchors behaviour to concrete steps and UI interactions
* Promotes consistency across multi-step flows

---

## Prompt Strategy: React Within a Step

Ask the model to respond from the perspective of a persona *at a specific step* of a journey.

### Example Prompt: Simulate Step Experience

```plaintext
Here is an Experience Notation journey:

Persona: Apprehensive Student
  Traits: { tech_savvy=false, age=17 }
  Experience: Nervous about using online platforms

Event: Course Onboarding
  Step: Start registration
    User: Apprehensive Student
    Action: Visits course portal
    UI-Element: Landing Page

Prompt:
As the persona above, describe how they feel in the 'Start registration' step.
```

### Sample Output

```plaintext
"I’m unsure where to begin. There’s a lot going on visually, and I worry I might click the wrong thing."
```

---

## Prompt Strategy: Roleplay Conversation from Journey

Provide a `.expn` with at least two personas and a relevant `Event:` block. Then ask the model to simulate a realistic interaction based on the journey.

### Example Prompt: Dialogue Simulation from Journey

```plaintext
Experience Notation:

Persona: Support Agent
  Traits: { empathy=high }
  Experience: Calm and professional

Persona: Confused User
  Traits: { tech_savvy=false }
  Experience: Lost in the navigation process

Event: Request Assistance
  Step: User opens help window
    User: Confused User
    Action: Clicks on the help button
    UI-Element: Header Navigation

  Step: Agent engages
    User: Support Agent
    Action: Starts a live chat greeting
    UI-Element: Chat Window

Prompt:
Write a realistic conversation between these two personas during the 'Request Assistance' event.
```


### Sample Output

```plaintext
Chat Window – Live Support Conversation 

Support Agent: 
Hello there! You’re through to course support. I’m here to help — what seems to be the trouble today? 

Confused User: 
Hi, sorry… I’m trying to register for a course, but I can’t figure out where to go. The page has so many buttons and I’m not sure what I’m doing. 

Support Agent: 
That’s absolutely fine — you’re not the only one who feels that way. I’ll guide you through it step by step. Could you tell me what you see on your screen right now? 

Confused User: 
There’s a big banner at the top, and some menu links. I clicked something earlier and it took me to a different page, but now I can’t find where I was. 

Support Agent: 
No worries — let’s get you back on track. Look at the top of the page; do you see a menu item that says “Courses” or “Register”? Confused User: Yes! There’s a “Courses” tab. 

Support Agent: 
Perfect. Please hover your mouse over that and a drop-down menu should appear. You’ll want to click “New Student Registration”. 

Confused User: 
Okay… I clicked it. Yes, now it says “Step 1: Create an Account”. 

Support Agent: 
Brilliant — you’re in the right place. From here, just fill in your name and email, and let me know if anything is unclear along the way. I’m right here with you. 

Confused User: 
Thank you… I really wasn’t sure what to do. This helps a lot. 

Support Agent: 
You’re very welcome — take your time, and don’t hesitate to message me again if you get stuck. You’ve got this.

```

---

## Tips for Effective Roleplay

* Always pair `Persona:` with related `Event:` and `Step:` context
* Use `Experience:` and `Metrics:` to influence tone and sentiment
* Ask the model to focus on a single step or simulate transitions
* Use `Adaptation:` to reflect behavioural evolution over time

---

Continue to [Generating Narrative From Journeys](narrative-generation.md) to explore how `.expn` models can be created directly through structured prompt engineering.
