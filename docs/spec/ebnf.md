# EBNF Grammar

This page presents the full formal grammar for Experience Notation, written in Extended Backus–Naur Form (EBNF). It defines the allowed structure and nesting of all constructs in a `.expn` file.

Experience Notation is whitespace-sensitive, with structure indicated through indentation. This grammar supports both human readability and precise programmatic parsing.

---

## Grammar Version

- **EBNF-Version:** 1.1  
- **Syntax-Version:** 1.0

---

## Overview

The grammar below defines the syntax rules for:

- File headers
- Events and steps
- Personas and actions
- Conditional logic
- Disruptions and environment
- Tagging, metadata, and referencing

You can use this grammar to:

- **Build parsers or validators**  
  Implement tooling that programmatically parses, validates, or converts `.expn` files.

- **Understand the structure of Experience Notation documents**  
  The EBNF acts as a definitive reference for authors, reviewers, and tool developers working with the DSL.

- **Guide large language models (LLMs)**  
  Use the grammar as a structured prompt to help LLMs generate syntactically valid `.expn` journeys from natural language descriptions.

---

## EBNF Definition

```ebnf
# Metadata:
#   Title: Experience Notation
#   EBNF-Version: 1.1
#   Syntax-Version: 1.0 
#   Author: Nikolaos Maniatis
#   Copyright © 2025 The Cato Bot Company Limited
#   Licence: Apache 2.0
#   Repository: https://github.com/context-notation/experience-notation


journey             = grammar_version , header , { blank | top_level } ;
# A journey document starts with the grammar version and a header,
# followed by any number of blank lines or top-level components (events or global personas).

grammar_version     = "EBNF-Version:" , wsp , version , nl ;
# Specifies which version of the Experience Notation grammar this document uses.

header              = "Syntax-Version:" , wsp , version , nl ,
                      "Journey-Title:" , wsp , text , nl ,
                      "Journey-Description:" , wsp , text , nl ;
# Declares the syntax version for this specific journey instance,
# and provides a title and description for human readability.

top_level           = event | persona_global ;
# Top-level elements can be Events or globally defined Personas.

# ----- EVENTS ---------------------------------------------
event               = "Event:" , wsp , text , nl , { indented_event_child } ;
# Each event begins with a title and can include indented children:
# steps, personas, metadata, tags, conditionals, etc.

indented_event_child = ind1 , ( id_line | tag_line | env_factors | parallel_events |
                                disruption | step | persona_block | conditional |
                                reference | comment ) ;
# Event children must be indented and may include metadata, environmental context,
# steps, personas, branching logic, references, or comments.

env_factors         = "Environmental-Factors:" , wsp , text , nl ;
# Describes environmental or contextual factors affecting the event.

parallel_events     = "Parallel-Events:" , wsp , csv(text) , nl ;
# Lists other events that occur concurrently with this one.

disruption          = "Disruption:" , wsp , text , nl ;
# Describes any interruption, exception, or breakdown within the journey.

# ----- STEPS ----------------------------------------------
step                = ind1 , "Step:" , wsp , text , nl ,
                      { ind2 , ( id_line | tag_line | user_role | action |
                                 ui_element | conditional | persona_block | reference ) } ;
# A step is a sequence within an event.
# It contains further indented items such as user actions, roles, conditions, and personas.
# Step must include at least one user_role and one action.

user_role           = "User:" , wsp , text , nl ;
# Declares the user or actor performing this step.

action              = "Action:" , wsp , text , nl ;
# Describes what the user or system does.

ui_element          = "UI-Element:" , wsp , text , nl ;
# Specifies the part of the interface involved in the step.

# ----- PERSONA (inline, context-specific) -----------------
persona_block       = ind2? , "Persona:" , wsp , text , nl ,
                      { ind3 , ( id_line | meta_line | experience |
                                 metrics | interaction | adaptation |
                                 reference | external_source_line ) } ;
# Defines a persona relevant to this event or step.
# May include structured metadata, behavioural traits, metrics, context, or an external reference.

experience          = "Experience:" , wsp , text , nl ;
interaction         = "Interaction:" , wsp , text , nl ;
adaptation          = "Adaptation:" , wsp , text , nl ;
# Narrative descriptions of how the persona engages, responds, or adapts during this point.

metrics             = "Metrics:" , wsp , "{" , wsp? , metric_pairs , wsp? , "}" , nl ;
# Captures performance or behavioural metrics in key=value format.

# ----- IDENTIFIERS & TAGS ---------------------------------
id_line             = "ID:" , wsp , identifier , nl ;
tag_line            = "Tag:" , wsp , csv(identifier) , nl ;
# Used to uniquely identify or categorise events, steps, or personas.

# ----- META BLOCK -----------------------------------------
meta_line           = "Meta:" , wsp , "{" , wsp? , meta_pairs , wsp? , "}" , nl ;
meta_pairs          = meta_pair , { "," , wsp? , meta_pair } ;
meta_pair           = identifier , "=" , text ;
# Provides structured, arbitrary metadata using key=value pairs.

# ----- METRICS -------------------------------------------
metric_pairs        = metric_pair , { "," , wsp? , metric_pair } ;
metric_pair         = metric_key , "=" , metric_value ;
metric_key          = identifier ;
metric_value        = number | text ;
# Metrics can be textual or numeric.

# ----- CONDITIONALS ---------------------------------------
conditional         = "Conditional:" , wsp , conditional_expr , nl ;
conditional_expr    = if_then | if_then_else ;
if_then             = "IF" , wsp , text , wsp , "THEN" , wsp , text ;
if_then_else        = if_then , wsp , "ELSE" , wsp , text ;
# Support for basic branching logic with optional ELSE clause.

# ----- REFERENCES ----------------------------------------
reference           = "Ref:" , wsp , identifier , nl ;
# Allows referencing other elements by their ID.

# ----- EXTERNAL REFERENCES --------------------------------
external_source_line = "External-Source:" , wsp , text , nl ;
# Specifies an external URI or identifier for a persona definition.
# This allows linking to persona data managed outside the current .expn document.

# ----- GLOBAL PERSONAS ------------------------------------
persona_global      = "Persona:" , wsp , text , nl ,
                      { ind1 , ( id_line | meta_line | experience |
                                 metrics | interaction | adaptation |
                                 reference | external_source_line ) } ;
# Allows personas to be declared globally, not just within specific steps or events.

# ----- LEXICAL STRUCTURE ----------------------------------
identifier          = alpha , { alpha | digit | "_" } ;
alpha               = "A"..."Z" | "a"..."z" ;
digit               = "0"..."9" ;
any_char            = ? any valid character except control characters ? ;
version             = digit , "." , digit ;
# A basic version format, e.g., 1.0

text                = { any_char - nl } ;
# Any string excluding newlines.

number              = [ "-" ] , digit , { digit } , [ "." , digit , { digit } ] ;
# Numeric values for metrics and other quantifiable data.

csv(X)              = X , { "," , wsp? , X } ;
# Helper function for comma-separated lists of values.

ind1                = 2*" " ;
ind2                = 4*" " ;
ind3                = 6*" " ;
# Indentation levels (2, 4, 6 spaces) to structure hierarchy.

wsp                 = " " | "\t" ;
nl                  = "\n" | "\r\n" ;
blank               = nl ;
```

---

## Notes

- Indentation is significant and should be consistent (spaces, not tabs)
- Comments start with `#` and may appear on any line
- String values can be quoted or unquoted, unless whitespace or symbols are used
- Reserved keywords (like `Event:`, `Step:`, `IF:`) must appear exactly as defined

For structural constraints and field-level types, refer to the [JSON Schema Reference](json-schema.md).
