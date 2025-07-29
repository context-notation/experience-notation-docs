# Example: Contextual Factors

## Purpose

This example shows how to incorporate context-aware elements such as disruptions, environment shifts, and unexpected conditions using `Disruption:` and `Environmental-Factors:`.

## Features Demonstrated

* Use of `Disruption:` to model friction in an experience
* Use of `Environmental-Factors:` to describe influencing context
* Use of `Tag:` for quick categorisation

## Annotated Example

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Disrupted Commute
Journey-Description: Captures how external conditions affect a journey

Event: Begin Journey
  Step: Check train schedule
    User: Commuter
    Action: Opens train app
    UI-Element: Mobile App
    Environmental-Factors: { weather="snow", network="unstable" }
    Tag: [planning]

  Step: Receive delay alert
    User: Commuter
    Action: Gets push notification
    UI-Element: Mobile App
    Disruption: Train service suspended due to weather
    Tag: [friction, alert]

Event: Reroute Journey
  Step: Search alternate routes
    User: Commuter
    Action: Opens maps and checks ride options
    UI-Element: Navigation App

  Step: Book ride-share
    User: Commuter
    Action: Reserves car
    UI-Element: Ride-share App
    Environmental-Factors: { surge_pricing=true }
```

## What You Can Learn

* How to model situational and external variables
* How to communicate breakdowns and recoveries
* How `Tag:` and `Environmental-Factors:` enhance semantic clarity

Continue to [Modular Journeys](modular.md) to explore structuring experiences across files or reusable patterns.
