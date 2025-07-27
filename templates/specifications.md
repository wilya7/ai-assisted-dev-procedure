# Technical Specifications Template
*Phase 2 - Specification Development*

## Project Information
**Project Name:** [Your project name]  
**Date:** [Current date]  
**Author:** [Your name]  
**Phase:** 2.1 - Technical Specification Brainstorming → 2.2 - Specification Iteration and Validation

---

## Prerequisites
- [ ] Completed Intent Document from Phase 1.1
- [ ] Completed Negative Space Map from Phase 1.2
- [ ] Code Reuse Assessment from Phase 1.1

---

## Phase 2.1: Technical Specification Brainstorming (Socratic Design Dialog)

### LLM Input Template

```
I need to develop technical specifications for my data science tool. I have completed the foundational analysis:

INTENT DOCUMENT:
[Copy complete Intent Document from Phase 1.1]

NEGATIVE SPACE MAP:
[Copy complete Negative Space Map from Phase 1.2 - all identified failure modes and constraints]

REUSE OPPORTUNITIES:
[Copy reuse assessment from Phase 1.1]

Act as my Socratic teacher to help me work backwards from my goals to implementation. I need to systematically explore design decisions, data structures, algorithms, user interfaces, and technical approaches.

Focus on helping me discover:
- What data structures and file formats will support my goals while avoiding the failure modes we identified?
- What algorithmic approaches will handle the edge cases and scale requirements?
- How should components interact to prevent the integration disasters we mapped?
- What user interface and error handling will make the tool robust and usable?

Ask ONE question at a time, building on my responses. Help me think through the implications of each design choice before moving to the next decision.

Start with the highest-level architectural decisions and progressively get more specific.
```

### Design Exploration Notes

#### Data Structures and File Formats
**Design Decision:** [What data structures will you use?]  
**Rationale:** [Why this choice? How does it avoid identified failure modes?]  
**Trade-offs:** [What are you giving up? What are you gaining?]

#### Algorithmic Approaches
**Design Decision:** [What algorithms/methods will you implement?]  
**Rationale:** [How do these handle edge cases and scale requirements?]  
**Trade-offs:** [Performance vs. simplicity vs. accuracy considerations]

#### Component Architecture
**Design Decision:** [How will major components interact?]  
**Rationale:** [How does this prevent integration disasters from Phase 1.2?]  
**Trade-offs:** [Modularity vs. performance vs. complexity]

#### User Interface Design
**Design Decision:** [Command line? Jupyter notebook? Scripts? Functions?]  
**Rationale:** [How does this serve your users and use cases?]  
**Trade-offs:** [Ease of use vs. flexibility vs. automation potential]

#### Error Handling Strategy
**Design Decision:** [How will you handle failures and edge cases?]  
**Rationale:** [How does this address failure modes from Phase 1.2?]  
**Trade-offs:** [Robustness vs. performance vs. code complexity]

#### Code Reuse Integration
**Design Decision:** [Which existing components will you adapt/reuse?]  
**Rationale:** [How do these fit with your new architecture?]  
**Trade-offs:** [Development speed vs. customization vs. learning value]

### Draft Specifications Output

#### System Architecture
[High-level description of how components fit together]

#### Data Flow Design
[Step-by-step description of data transformations]

#### Input Processing
- **File handling:** [How files are read, validated, preprocessed]
- **Error detection:** [Input validation and error handling]
- **Data structures:** [Internal representation of data]

#### Core Processing Logic
- **Main algorithms:** [Key computational approaches]
- **Performance considerations:** [Memory usage, computational complexity]
- **Edge case handling:** [How unusual inputs are managed]

#### Output Generation
- **File formats:** [What files are created and how]
- **Visualization components:** [Plots, charts, reports]
- **Summary statistics:** [What analyses are performed]

#### Integration Points
- **Dependencies:** [External libraries and tools required]
- **Reused components:** [Specific functions/modules from previous projects]
- **Testing strategy:** [How each component will be validated]

---

## Phase 2.2: Specification Iteration and Validation

### Deep Reflection Checklist

#### Completeness Review
- [ ] Do the specifications address all goals from the Intent Document?
- [ ] Are all failure modes from the Negative Space Map mitigated?
- [ ] Are the design decisions internally consistent?
- [ ] Can you trace a clear path from specifications to working implementation?

#### Failure Mode Mitigation Check
**Data Flow Failures:** [How are these addressed in specifications?]

**Assumption Violations:** [How are these handled in design?]

**Integration Disasters:** [How does architecture prevent these?]

**Scale-Up Failures:** [How does design handle larger data/usage?]

#### Implementation Feasibility
- [ ] Are there any design decisions you can't explain clearly?
- [ ] Are there any fundamental architectural choices you're uncertain about?
- [ ] Can you visualize the complete data flow from input to output?
- [ ] Do you understand how each component will be implemented?

### Optional LLM Consultation Areas

#### Complex Algorithmic Decisions
**Issue:** [Describe specific algorithmic challenge]  
**LLM Input:** [Specific question about algorithms, data structures, or optimization]  
**Resolution:** [How you resolved the issue based on consultation]

#### Data Structure Optimization
**Issue:** [Describe data structure challenge]  
**LLM Input:** [Specific question about data organization or performance]  
**Resolution:** [Design decision and rationale]

#### Error Handling Strategies
**Issue:** [Describe error handling challenge]  
**LLM Input:** [Specific question about robustness or user experience]  
**Resolution:** [Error handling approach selected]

#### Integration Approach Refinement
**Issue:** [Describe component integration challenge]  
**LLM Input:** [Specific question about architecture or interfaces]  
**Resolution:** [Integration strategy selected]

### Final Specifications

#### System Overview
[Complete description of tool architecture and purpose]

#### Technical Requirements
- **Python version:** [Required version and key libraries]
- **Dependencies:** [All external packages needed]
- **Environment:** [Development and deployment environment needs]

#### Component Specifications

##### Component 1: [Name]
**Purpose:** [What this component does]  
**Inputs:** [Data types, formats, requirements]  
**Processing:** [Algorithmic approach, key steps]  
**Outputs:** [Data types, formats, guarantees]  
**Error Handling:** [How failures are managed]  
**Testing:** [How component will be validated]

##### Component 2: [Name]
**Purpose:** [What this component does]  
**Inputs:** [Data types, formats, requirements]  
**Processing:** [Algorithmic approach, key steps]  
**Outputs:** [Data types, formats, guarantees]  
**Error Handling:** [How failures are managed]  
**Testing:** [How component will be validated]

[Continue for all major components...]

#### Data Flow Specification
1. **Step 1:** [Detailed description of first processing step]
2. **Step 2:** [Detailed description of second processing step]
3. **Step N:** [Detailed description of final processing step]

#### Interface Specifications
**User Interface:** [How users interact with the tool]  
**Input Interface:** [File formats, parameters, options]  
**Output Interface:** [File formats, visualization, reports]  
**Error Interface:** [How errors are communicated to users]

#### Performance Specifications
**Expected Performance:** [Runtime, memory usage for typical cases]  
**Scalability Limits:** [Maximum data sizes, computational limits]  
**Resource Requirements:** [Hardware and software needs]

---

## Phase Completion Criteria

### Decision Criteria for Moving to Phase 3.1
- [ ] You can confidently explain every design decision and its rationale
- [ ] All major failure modes from Phase 1.2 are addressed in the specifications
- [ ] You can visualize the complete data flow from input to output
- [ ] No remaining uncertainty about fundamental architectural choices
- [ ] The specifications feel complete enough for systematic decomposition

### Quality Validation
- [ ] Specifications are internally consistent
- [ ] All requirements from Intent Document are addressed
- [ ] Failure mitigation strategies are clearly defined
- [ ] Implementation path is clear and feasible
- [ ] Code reuse opportunities are properly integrated

---

## Next Steps
- [ ] Review specifications one final time
- [ ] Ensure all design decisions have clear rationales
- [ ] Prepare for Phase 3.1 (Atomic Unit Decomposition)
- [ ] Consider context window reset using Phase Transition Template

---

**Template Version:** 1.0  
**Last Updated:** [Date]  
**Source:** AI-Assisted Development Procedure

**Critical Time Allocation Note:** Phases 1-2 should consume approximately **67% of total project time** to ensure robust design foundation.