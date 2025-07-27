# Negative Space Mapping Template
*Phase 1.2 - Socratic Failure Mode Analysis*

## Project Information
**Project Name:** [Your project name]  
**Date:** [Current date]  
**Author:** [Your name]  
**Phase:** 1.2 - Negative Space Mapping (Socratic Failure Mode Analysis)

---

## Prerequisites
- [ ] Completed Intent Document from Phase 1.1
- [ ] Handwritten draft reviewed and validated
- [ ] Ready for systematic failure mode exploration

---

## Overview
**Purpose:** Systematically explore failure modes across four dimensions before design begins  
**Method:** Engage LLM as Socratic teacher to discover potential problems  
**Output:** Comprehensive Negative Space Map documenting all identified failure modes

---

## 1.2.1 Data Flow Failure Modes

### LLM Input Template

```
I'm developing [brief tool description from Intent Document].

Here is my complete Intent Document:
[Copy entire Intent Document]

Here are my data transformations: [extract and list each step where data gets modified/filtered/sampled/aggregated from Intent Document].

Act as my Socratic teacher. Ask me probing questions to help me discover how each transformation could break downstream processes. Focus on edge cases where the transformation could produce unexpected output formats, empty datasets, or violated assumptions that later components depend on.

Ask ONE question at a time, building on my responses.
```

### Dialogue Notes
**LLM Question 1:** [First question about data transformations]  
**My Response:** [Your answer and insights]  
**Follow-up insights:** [What this revealed about potential failures]

**LLM Question 2:** [Second question building on your response]  
**My Response:** [Your answer and insights]  
**Follow-up insights:** [What this revealed about potential failures]

[Continue documenting the dialogue...]

### Identified Data Flow Failure Modes

#### Transformation 1: [Name of data transformation]
**Potential Failures:**
- [Failure mode 1: description and impact]
- [Failure mode 2: description and impact]
- [Failure mode 3: description and impact]

#### Transformation 2: [Name of data transformation]
**Potential Failures:**
- [Failure mode 1: description and impact]
- [Failure mode 2: description and impact]

[Continue for all transformations...]

### Completion Check
- [ ] Can confidently answer: "How could each data transformation create impossible requirements for downstream components?"

---

## 1.2.2 Assumption Violations

### LLM Input Template

```
For my project [description from Intent Document], I'm making these assumptions: [extract all assumptions from Intent Document about data format, user behavior, computational resources, biological phenomena, etc.].

Be my Socratic teacher. Help me discover what happens when each assumption is false. Ask probing questions to uncover hidden assumptions I haven't listed and explore realistic scenarios where my stated assumptions break.

Focus on assumptions that, if violated, would require fundamental design changes rather than minor fixes.
```

### Dialogue Notes
**LLM Question 1:** [First question about assumptions]  
**My Response:** [Your answer and insights]  
**Hidden assumptions discovered:** [New assumptions you identified]

**LLM Question 2:** [Second question building on your response]  
**My Response:** [Your answer and insights]  
**Hidden assumptions discovered:** [New assumptions you identified]

[Continue documenting the dialogue...]

### Identified Assumption Violations

#### Stated Assumptions
**Assumption 1:** [Original assumption from Intent Document]  
**Violation scenarios:**
- [Scenario 1: when/how this could be false]
- [Consequences: what breaks if this assumption fails]
- [Design impact: fundamental changes required]

**Assumption 2:** [Original assumption from Intent Document]  
**Violation scenarios:**
- [Scenario 1: when/how this could be false]
- [Consequences: what breaks if this assumption fails]
- [Design impact: fundamental changes required]

[Continue for all stated assumptions...]

#### Hidden Assumptions Discovered
**Hidden Assumption 1:** [Assumption you weren't aware you were making]  
**Violation scenarios:**
- [How this could be false]
- [Consequences if violated]
- [Design impact required]

**Hidden Assumption 2:** [Another discovered assumption]  
**Violation scenarios:**
- [How this could be false]
- [Consequences if violated]
- [Design impact required]

[Continue for all hidden assumptions...]

### Completion Check
- [ ] Have identified assumptions that could cascade into system-wide design changes
- [ ] Have uncovered hidden assumptions not originally listed

---

## 1.2.3 Integration Disasters

### LLM Input Template

```
My tool will have these major components: [extract components from Intent Document and list each script/module and its primary responsibility].

Act as my Socratic teacher. Help me discover how component interactions could create impossible requirements. Ask questions about how Component A's edge cases could make Component B's job impossible, or how optimizing for Component X might break Component Y.

Pay special attention to shared data structures and intermediate file formats.
```

### Dialogue Notes
**LLM Question 1:** [First question about component interactions]  
**My Response:** [Your answer and insights]  
**Integration risks discovered:** [What interaction problems were revealed]

**LLM Question 2:** [Second question building on your response]  
**My Response:** [Your answer and insights]  
**Integration risks discovered:** [What interaction problems were revealed]

[Continue documenting the dialogue...]

### Identified Integration Disasters

#### Component Interaction 1: [Component A] → [Component B]
**Potential Disasters:**
- [How Component A's edge cases break Component B]
- [Shared data structure conflicts]
- [Performance optimization conflicts]

#### Component Interaction 2: [Component B] → [Component C]
**Potential Disasters:**
- [How Component B's failures cascade to Component C]
- [File format incompatibilities]
- [Timing or sequencing issues]

[Continue for all component pairs...]

#### Shared Resources Conflicts
**Shared Data Structure 1:** [Name and description]  
**Conflict scenarios:**
- [How different components might use this incompatibly]
- [What happens when structure needs change for one component]

**Intermediate File Format 1:** [Name and description]  
**Conflict scenarios:**
- [How different components might interpret this differently]
- [What happens with format evolution needs]

### Completion Check
- [ ] Understand how each component's failure modes affect every other component
- [ ] Have identified shared resource conflicts

---

## 1.2.4 Scale-Up Failures

### LLM Input Template

```
My tool is designed for [current scope from Intent Document: data size, complexity, etc.] but may need to handle [realistic scale-up scenarios from Intent Document].

Be my Socratic teacher. Ask questions to help me identify what works for simple cases but breaks at realistic scale. Focus on computational complexity, memory usage, user interface complexity, and maintenance overhead.
```

### Dialogue Notes
**LLM Question 1:** [First question about scalability]  
**My Response:** [Your answer and insights]  
**Scale limitations discovered:** [What scale problems were revealed]

**LLM Question 2:** [Second question building on your response]  
**My Response:** [Your answer and insights]  
**Scale limitations discovered:** [What scale problems were revealed]

[Continue documenting the dialogue...]

### Identified Scale-Up Failures

#### Computational Complexity Issues
**Algorithm/Process 1:** [Name of computational process]  
**Scale-up problems:**
- [How performance degrades with larger data]
- [Memory usage growth patterns]
- [Processing time implications]

**Algorithm/Process 2:** [Name of computational process]  
**Scale-up problems:**
- [How performance degrades with larger data]
- [Memory usage growth patterns]
- [Processing time implications]

#### User Interface Complexity
**Current UI approach:** [How users interact with tool]  
**Scale-up problems:**
- [How UI becomes unwieldy with more data/features]
- [Configuration complexity growth]
- [Result interpretation challenges]

#### Maintenance Overhead
**Current maintenance plan:** [How tool will be maintained]  
**Scale-up problems:**
- [How maintenance effort grows with usage]
- [Code complexity growth patterns]
- [Documentation and support needs]

### Completion Check
- [ ] Understand which design decisions are scale-limiting
- [ ] Have identified computational, UI, and maintenance scale problems

---

## Negative Space Map Consolidation

### Cross-Dimensional Failure Patterns

#### Critical Failure Modes (appear in multiple dimensions)
**Failure Mode 1:** [Description]  
**Appears in:** [Which dimensions: Data Flow, Assumptions, Integration, Scale-up]  
**Cascading effects:** [How this failure could trigger others]  
**Priority level:** [High/Medium/Low based on likelihood and impact]

**Failure Mode 2:** [Description]  
**Appears in:** [Which dimensions: Data Flow, Assumptions, Integration, Scale-up]  
**Cascading effects:** [How this failure could trigger others]  
**Priority level:** [High/Medium/Low based on likelihood and impact]

[Continue for all cross-dimensional failures...]

#### Single-Dimension Failures
**High-Impact Data Flow Failures:**
- [Failure mode: brief description and impact]
- [Failure mode: brief description and impact]

**High-Impact Assumption Violations:**
- [Failure mode: brief description and impact]
- [Failure mode: brief description and impact]

**High-Impact Integration Disasters:**
- [Failure mode: brief description and impact]
- [Failure mode: brief description and impact]

**High-Impact Scale-Up Failures:**
- [Failure mode: brief description and impact]
- [Failure mode: brief description and impact]

### Mitigation Strategy Notes

#### Top Priority Mitigations (for cross-dimensional failures)
**For [Critical Failure Mode 1]:**
- [Potential mitigation approach]
- [Design implications]
- [Implementation considerations]

**For [Critical Failure Mode 2]:**
- [Potential mitigation approach]
- [Design implications]
- [Implementation considerations]

#### Design Principles to Prevent Failures
1. [Design principle to avoid data flow failures]
2. [Design principle to handle assumption violations]
3. [Design principle to prevent integration disasters]
4. [Design principle to enable scale-up]

---

## Final Negative Space Map Summary

### Most Critical Failure Modes to Address in Design
1. **[Failure Mode Name]** - [Brief description and why it's critical]
2. **[Failure Mode Name]** - [Brief description and why it's critical]
3. **[Failure Mode Name]** - [Brief description and why it's critical]
4. **[Failure Mode Name]** - [Brief description and why it's critical]
5. **[Failure Mode Name]** - [Brief description and why it's critical]

### Design Requirements Generated
- [Requirement 1: derived from failure mode analysis]
- [Requirement 2: derived from failure mode analysis]
- [Requirement 3: derived from failure mode analysis]
- [Requirement 4: derived from failure mode analysis]

### Architecture Constraints Identified
- [Constraint 1: limitation discovered through failure analysis]
- [Constraint 2: limitation discovered through failure analysis]
- [Constraint 3: limitation discovered through failure analysis]

---

## Phase Completion Criteria
- [ ] Completed all four failure mode analysis dimensions
- [ ] Identified cross-dimensional failure patterns
- [ ] Documented cascading effects for critical failures
- [ ] Generated design requirements from failure analysis
- [ ] Created prioritized list of failure modes to address
- [ ] Ready to proceed with informed specification development

---

## Next Steps
- [ ] Review Negative Space Map for completeness
- [ ] Prepare materials for Phase 2.1 (Specification Development)
- [ ] Consider context window reset using Phase Transition Template
- [ ] Carry forward Intent Document + Negative Space Map to next phase

---

**Template Version:** 1.0  
**Last Updated:** [Date]  
**Source:** AI-Assisted Development Procedure

**Phase Transition Note:** Before proceeding to Phase 2.1, consider using the Phase Transition Template to start fresh with a clean context window, carrying forward only your Intent Document and completed Negative Space Map.