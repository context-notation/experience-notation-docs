# Example: Modular Journeys

## Purpose

This example demonstrates how to compose journeys from reusable parts. Using `Ref:` and `Tag:`, you can construct modular journeys that reference other models or templates.

## Features Demonstrated

* Use of `Ref:` to reference external events or components
* Use of `Tag:` to classify and filter journey elements
* Reusable structure and modular organisation

## Annotated Example

```expn
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Modular Checkout Flow
Journey-Description: A checkout process built from shared journey components

External-Source: https://example.com/common/checkout-base.expn

Event: Cart Review
  Step: Review items
    User: Shopper
    Action: Reviews cart contents
    UI-Element: Cart Page
    Tag: [cart, pre-checkout]

  Step: Proceed to checkout
    User: Shopper
    Action: Clicks checkout button
    UI-Element: Cart Page

Event: Checkout Flow
  Ref: common-checkout-base
  Tag: [reused, checkout]

Event: Post-Purchase
  Step: Show thank you message
    User: Shopper
    Action: Sees confirmation screen
    UI-Element: Confirmation Page
    Tag: [post-checkout]
```

## What You Can Learn

* How to structure a journey using referenced components
* How `Ref:` allows for cleaner, more maintainable flows
* How tagging improves navigation, filtering, and classification

Continue to [Comprehensive CX Journey](full-journey.md) to see how all features come together in a complex scenario.
