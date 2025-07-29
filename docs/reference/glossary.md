# **Glossary**

This glossary defines key terms used throughout the Experience Notation documentation.

---

### **Adaptation**

A narrative or behavioural description of how a persona may change over the course of a journey. Optional within a `Persona:` block.

### **Conditional**

A branching block used within a `Step:` that describes alternate outcomes depending on a stated condition, using `IF`, `THEN`, and `ELSE` fields.

### **EBNF (Extended Backus–Naur Form)**

A formal notation used to describe the syntax rules of Experience Notation. Used to guide both human authors and automated validation.

### **Event**

A major unit of experience within a journey, composed of one or more sequential `Step:` blocks.

### **Experience**

A freeform emotional or contextual description of a persona’s state at the beginning of the journey.

### **External-Source**

A URL reference to an external resource or document relevant to the journey context.

### **Journey**

A top-level `.expn` file representing a structured user experience, composed of metadata, personas, and one or more events.

### **Metrics**

Quantitative or qualitative persona state values (e.g. `mood=low`, `energy=medium`). Used to enrich simulation or roleplay.

### **Persona**

A named user or agent defined in the `.expn` file. Includes `Traits:`, `Experience:`, `Metrics:`, and optionally `Adaptation:`.

### **Step**

An individual action taken within an `Event:`. Includes subfields such as `User:`, `Action:`, `UI-Element:`, and optionally `Conditional:`.

### **Tag**

A keyword or category assigned to a `Step:` to support indexing, classification, or filtering.

### **Traits**

Key–value pairs that define behavioural or demographic characteristics of a persona.

### **UI-Element**

The interface component or system element that the persona interacts with in a given step.

### **User**

The name of the persona involved in a given `Step:`.

---

If you're looking for syntax specifics, see the [EBNF Grammar](../spec/ebnf.md) or [JSON Schema Reference](../spec/json-schema.md).
