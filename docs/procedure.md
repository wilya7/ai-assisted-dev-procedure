# Table of Contents

1.  [Living Document Update Prompt](#org9bcff7d)
    1.  [Update Protocol](#org1c832ca)
2.  [Overview](#orgb9b7e9d)
3.  [Human-LLM Interaction Framework](#orgdd973e9)
    1.  [Clear handoff specifications for each phase](#orgc915691)
    2.  [Key Principle](#org96ff3d6)
    3.  [Context Window Management](#org5564970)
        1.  [Phase Transition Template](#org0634823)
        2.  [**When to Use Clean Handoffs**:](#org4f785f1)
        3.  [Benefits:](#org701fe9e)
4.  [Phase 1: Project Bootstrap](#org5dabba0)
    1.  [1.1 Goal Clarification](#org22ade4c)
        1.  [HUMAN ACTIVITY (No LLM involvement)](#orgb8321bc)
    2.  [1.2 Negative Space Mapping (Socratic Failure Mode Analysis)](#org2cf1213)
        1.  [1.2.1 Data Flow Failure Modes](#org9174631)
        2.  [1.2.2 Assumption Violations](#orga85bdd1)
        3.  [1.2.3 Integration Disasters](#orgb3fd2b1)
        4.  [1.2.4 Scale-Up Failures](#orgb0dfa57)
5.  [Phase 2: Specification Development](#org4403c4b)
    1.  [2.1 Technical Specification Brainstorming (Socratic Design Dialog)](#org395f583)
        1.  [HUMAN INPUT TO LLM:](#orgee63b56)
        2.  [Workflow](#org89efa28)
        3.  [Phase Transition Note](#orgae04a9a)
    2.  [2.2 Specification Iteration and Validation](#org6ebf16b)
        1.  [Iterative refinement process](#org5b9c16e)
        2.  [Decision criteria for moving to Phase 3.1](#org403ab5a)
6.  [Phase 3: Atomic Unit Decomposition](#orgda62028)
    1.  [3.1 Specification Decomposition (Two-Document Approach)](#orgdd80d9c)
        1.  [3.1.1 Generate Decomposition Documents](#org8ea04c5)
        2.  [3.2 Decomposition Quality Control](#org4b727ca)
7.  [Phase 4: Systematic Code Development](#org13a0332)
    1.  [4.1 Repository Setup](#orgf898574)
        1.  [Setup Tasks](#org154d03d)
    2.  [4.2 Per-Unit Development Workflow](#org9814c8c)
        1.  [Step 1: Prompt Execution](#orga7b40ff)
        2.  [Step 2: Code Understanding (Learning Phase)](#org9281246)
        3.  [Step 3: Integration](#org699091c)
        4.  [Step 4: Testing](#org8f18bd0)
        5.  [Step 5: Optional Troubleshooting](#org8527594)
        6.  [Step 6: Version Control](#org44529e8)
        7.  [Step 7: Documentation](#org27a476e)
        8.  [Step 8: Progress Tracking](#org17c8e42)
    3.  [4.3 Integration Milestones](#org97eed2f)
        1.  [Milestone Tasks](#orgf80069d)
8.  [Phase 5: Quality Assurance and Finalization](#orgd149375)
    1.  [5.1 Final Integration Testing](#org2e95ad8)
    2.  [5.2 Documentation Finalization](#org66ee23d)
    3.  [5.3 Repository Quality Standards](#orgc5cc863)
        1.  [Quality Checklist](#org1a36b4f)
9.  [Workflow Timing Guidelines](#org92a40d1)
    1.  [Phase Distribution](#orge522f56)
    2.  [Total Range](#org6ae4b7b)
    3.  [Key Insight](#orga82a224)
10. [Success Criteria](#org3a62132)
11. [Adaptation Guidelines](#org67eab4f)
    1.  [For simpler projects](#orgf160839)
    2.  [For more complex projects](#orgf0f3c50)
    3.  [Learning focus adjustments](#org2db42ce)
12. [Complete Human-LLM Workflow Summary](#org9bc010c)
    1.  [Key Insight](#org4d4fd97)



<a id="org9bcff7d"></a>

# Living Document Update Prompt

    This is a living document containing a systematic procedure for AI-assisted software development in data science. I've been testing this procedure on real projects and need to update it based on practical experience.
    
    CURRENT DOCUMENT:
    [Paste the complete procedure document]
    
    MY TESTING EXPERIENCE:
    [Describe what worked well, what didn't work, specific problems encountered, timing issues, workflow bottlenecks, etc.]
    
    SPECIFIC AREAS FOR IMPROVEMENT:
    [List particular sections, phases, or techniques that need refinement]
    
    Please help me refine this procedure by:
    1. Identifying which parts of my experience suggest systematic improvements vs. one-off issues
    2. Proposing specific modifications to address the problems I encountered
    3. Suggesting additional guidance or clarifications for areas that were unclear in practice
    4. Maintaining the overall structure and philosophy while improving practical effectiveness
    5. Updating the version number (current: X.X → next: X.Y) 
    
    Focus on making the procedure more robust and executable based on real-world usage while preserving the systematic approach and learning objectives.
    
    Ask me clarifying questions about my experience if needed to provide the most helpful refinements.


<a id="org1c832ca"></a>

## Update Protocol

-   Test the procedure on real projects
-   Document what works and what needs improvement
-   Use the prompt above to get systematic refinements
-   Increment version number for each refinement cycle
-   Maintain the core philosophy: systematic design thinking + learning-focused implementation + research-grade quality


<a id="orgb9b7e9d"></a>

# Overview

This procedure systematically develops focused, project-specific data analysis tools while maintaining research-grade quality standards. The workflow emphasizes thorough upfront planning to minimize debugging time and maximize learning value through granular, testable code units.


<a id="orgdd973e9"></a>

# Human-LLM Interaction Framework


<a id="orgc915691"></a>

## Clear handoff specifications for each phase

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">Phase</th>
<th scope="col" class="org-left">Human Input</th>
<th scope="col" class="org-left">LLM Input</th>
<th scope="col" class="org-left">Human Output</th>
<th scope="col" class="org-left">LLM Output</th>
</tr>
</thead>
<tbody>
<tr>
<td class="org-right">1.1</td>
<td class="org-left">Manual drafting</td>
<td class="org-left">None</td>
<td class="org-left">Intent Document</td>
<td class="org-left">None</td>
</tr>

<tr>
<td class="org-right">1.2</td>
<td class="org-left">Intent Document</td>
<td class="org-left">Intent Document</td>
<td class="org-left">Negative Space Map</td>
<td class="org-left">Socratic failure questions</td>
</tr>

<tr>
<td class="org-right">2.1</td>
<td class="org-left">Intent + Negative Space + Reuse</td>
<td class="org-left">Intent + Negative Space + Reuse</td>
<td class="org-left">Draft Specifications</td>
<td class="org-left">Socratic design questions</td>
</tr>

<tr>
<td class="org-right">2.2</td>
<td class="org-left">Draft Specifications</td>
<td class="org-left">Optional: specific design challenges</td>
<td class="org-left">Final Specifications</td>
<td class="org-left">Optional: design guidance</td>
</tr>

<tr>
<td class="org-right">3.1</td>
<td class="org-left">Final Specs + Code Repos</td>
<td class="org-left">Final Specs + Code Repos</td>
<td class="org-left">Quality review</td>
<td class="org-left">Prompt Guide + Todo List</td>
</tr>

<tr>
<td class="org-right">4.X</td>
<td class="org-left">Prompts from Guide</td>
<td class="org-left">Individual prompts</td>
<td class="org-left">Working code units</td>
<td class="org-left">Code + explanations</td>
</tr>
</tbody>
</table>


<a id="org96ff3d6"></a>

## Key Principle

Documents created FOR LLMs are structured for machine consumption. Documents created BY LLMs are structured for human use. Documents created by humans FOR humans prioritize clarity and decision-making.


<a id="org5564970"></a>

## Context Window Management

**Problem**: Socratic questioning phases (1.2, 2.1) generate extensive dialogues that can overwhelm context windows and reduce focus in subsequent phases.
**Solution**: Use clean handoff transitions between major phases to maintain conversation focus and preserve only essential work products.


<a id="org0634823"></a>

### Phase Transition Template

    Phase Transition: Clean Handoff Prompt
    CONTEXT RESET FOR SYSTEMATIC DATA SCIENCE DEVELOPMENT
    
    I'm following a systematic procedure for AI-assisted data science tool development. I've completed [PREVIOUS PHASE] and need to begin [NEXT PHASE] with a fresh conversation context.
    COMPLETED WORK FROM PREVIOUS PHASE:
    
    [DOCUMENT TYPE - e.g., "FINAL INTENT DOCUMENT" or "VALIDATED TECHNICAL SPECIFICATIONS"]:
    
    [Insert complete final document from previous phase here]
    
    RELEVANT SUPPORTING MATERIALS:
    
        Code reuse opportunities identified: [brief list if applicable]
        Key constraints/requirements: [brief summary if relevant]
    
    NEXT PHASE REQUIREMENTS:
    
    I need to proceed with [NEXT PHASE NAME AND DESCRIPTION] according to this methodology:
    
    [Insert relevant section from the procedure document for the next phase]
    
    YOUR ROLE:
    
    [Specific instructions for LLM role in next phase - e.g., "Act as my Socratic teacher to help map failure modes" or "Help me decompose these specifications into atomic units"]
    READY TO BEGIN:
    
    [First specific prompt/question for the new phase]


<a id="org4f785f1"></a>

### **When to Use Clean Handoffs**:

-   **After Phase 1.2** -> Before Phase 2.1 (carry forward: Intent Document + Negative Space Map)
-   **After Phase 2.1** -> Before Phase 2.2 (carry forward: Intent + Negative Space + Draft Specifications)
-   **After Phase 2.2** -> Before Phase 3.1 (carry forward: Final Specifications + Reuse Assessment)
-   **After Phase 2.2** -> Before Phase 3.1 (carry forward: Final Specifications + Reuse Assessment)


<a id="org701fe9e"></a>

### Benefits:

-   Prevents context window bloat from lengthy Socratic dialogues
-   Maintains sharp focus for each development phase
-   Preserves essential work products while discarding conversational noise
-   Allows for more precise LLM interactions in later phases


<a id="org5dabba0"></a>

# Phase 1: Project Bootstrap


<a id="org22ade4c"></a>

## 1.1 Goal Clarification


<a id="orgb8321bc"></a>

### HUMAN ACTIVITY (No LLM involvement)

1.  1. Draft Intent Document by hand (pen and paper)

    -   Problem statement (what manual process are you replacing/optimizing?)
    -   Success criteria (quantifiable metrics: time savings, statistical power, etc.)
    -   Input/output specifications (file formats, data structure, expected volumes)
    -   Key constraints (timeline, computational resources, compatibility requirements)
    -   Stakeholders and collaboration requirements
    
    > **Why handwritten**: Handwriting engages deeper cognitive processes essential for establishing the project foundation clearly.

2.  2. Assess Code Reuse Opportunities (review existing repositories)

    -   Review previous projects for relevant patterns, functions, or approaches
    -   Identify specific components that could be reused or adapted
    -   Document existing solutions to avoid reinventing solved problems
    -   Note any consistency requirements with existing tools

3.  3. Validate Intent (human collaboration)

    -   Describing the tool to a colleague and noting their questions
    -   Writing 3-5 concrete usage examples with realistic data
    -   Identifying the **MVP core** (Minimum Viable Product: the single most critical feature that makes the tool useful - if you could only implement one feature, what would it be?)
    -   Confirming which parts are genuinely new vs. adaptations of existing work

4.  HUMAN OUTPUT

    Intent Document (typed version of handwritten draft, 1-2 pages max) including reuse assessment

5.  Benefits of Early Reuse Assessment

    -   Reduces development time by leveraging proven solutions
    -   Maintains consistency with existing tools for collaboration
    -   Focuses new development effort on genuinely novel problems
    -   Provides more accurate project timeline estimates
    -   Preserves learning value through adaptation rather than repetition


<a id="org2cf1213"></a>

## 1.2 Negative Space Mapping (Socratic Failure Mode Analysis)

**Process**: Engage LLM as Socratic teacher to systematically explore failure modes across four dimensions:


<a id="org9174631"></a>

### 1.2.1 Data Flow Failure Modes

1.  HUMAN INPUT TO LLM:

        I'm developing [brief tool description from Intent Document]. 
        
        Here is my complete Intent Document:
        [Copy entire Intent Document]
        
        Here are my data transformations: [extract and list each step where data gets modified/filtered/sampled/aggregated from Intent Document].
        
        Act as my Socratic teacher. Ask me probing questions to help me discover how each transformation could break downstream processes. Focus on edge cases where the transformation could produce unexpected output formats, empty datasets, or violated assumptions that later components depend on.
        
        Ask ONE question at a time, building on my responses.

2.  Workflow

    -   **LLM OUTPUT**: Series of probing questions
    -   **HUMAN ACTIVITY**: Answer questions, engage in dialogue
    -   **HUMAN OUTPUT**: Notes on discovered failure modes
    
    **Continue until you can confidently answer**: "How could each data transformation create impossible requirements for downstream components?"


<a id="orga85bdd1"></a>

### 1.2.2 Assumption Violations

1.  HUMAN INPUT TO LLM:

        For my project [description from Intent Document], I'm making these assumptions: [extract all assumptions from Intent Document about data format, user behavior, computational resources, biological phenomena, etc.].
        
        Be my Socratic teacher. Help me discover what happens when each assumption is false. Ask probing questions to uncover hidden assumptions I haven't listed and explore realistic scenarios where my stated assumptions break.
        
        Focus on assumptions that, if violated, would require fundamental design changes rather than minor fixes.

2.  Workflow

    -   **LLM OUTPUT**: Series of probing questions about assumptions
    -   **HUMAN ACTIVITY**: Answer questions, identify additional assumptions
    -   **HUMAN OUTPUT**: Notes on assumption violations and their consequences
    
    **Continue until**: You've identified assumptions that could cascade into system-wide design changes.


<a id="orgb3fd2b1"></a>

### 1.2.3 Integration Disasters

1.  HUMAN INPUT TO LLM:

        My tool will have these major components: [extract components from Intent Document and list each script/module and its primary responsibility].
        
        Act as my Socratic teacher. Help me discover how component interactions could create impossible requirements. Ask questions about how Component A's edge cases could make Component B's job impossible, or how optimizing for Component X might break Component Y.
        
        Pay special attention to shared data structures and intermediate file formats.

2.  Workflow

    -   **LLM OUTPUT**: Questions about component interactions
    -   **HUMAN ACTIVITY**: Analyze interactions, identify conflict scenarios
    -   **HUMAN OUTPUT**: Notes on integration failure modes
    
    **Continue until**: You understand how each component's failure modes affect every other component.


<a id="orgb0dfa57"></a>

### 1.2.4 Scale-Up Failures

1.  HUMAN INPUT TO LLM:

        My tool is designed for [current scope from Intent Document: data size, complexity, etc.] but may need to handle [realistic scale-up scenarios from Intent Document].
        
        Be my Socratic teacher. Ask questions to help me identify what works for simple cases but breaks at realistic scale. Focus on computational complexity, memory usage, user interface complexity, and maintenance overhead.

2.  Workflow

    -   **LLM OUTPUT**: Questions about scalability limitations
    -   **HUMAN ACTIVITY**: Consider scale implications
    -   **HUMAN OUTPUT**: Notes on scale-up failure modes
    
    **Continue until**: You understand which design decisions are scale-limiting.

3.  HUMAN OUTPUT

    Negative Space Map document (created by human, consolidating notes from all four dialogues) listing identified failure modes and their potential cascading effects.

4.  Phase Transition Note

    Before proceeding to Phase 2.1, consider using the Phase Transition Template (Section 3.3) to start fresh with a clean context window, carrying forward only your Intent Document and completed Negative Space Map.


<a id="org4403c4b"></a>

# Phase 2: Specification Development


<a id="org395f583"></a>

## 2.1 Technical Specification Brainstorming (Socratic Design Dialog)


<a id="orgee63b56"></a>

### HUMAN INPUT TO LLM:

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


<a id="org89efa28"></a>

### Workflow

-   **LLM OUTPUT**: Series of design exploration questions
-   **HUMAN ACTIVITY**: Answer questions, explore design implications, document design decisions
-   **HUMAN OUTPUT**: Draft technical specifications with rationale for each design decision

**Continue until**: You have systematically explored all major design decisions and their implications.


<a id="orgae04a9a"></a>

### Phase Transition Note

The extensive design dialogue in this phase may warrant a clean context reset before Phase 2.2 using the Phase Transition Template.


<a id="org6ebf16b"></a>

## 2.2 Specification Iteration and Validation


<a id="org5b9c16e"></a>

### Iterative refinement process

1.  1. Deep reflection on draft specifications (human-only)

    -   Do the specifications address all goals from the Intent Document?
    -   Are all failure modes from the Negative Space Map mitigated?
    -   Are the design decisions internally consistent?
    -   Can you trace a clear path from specifications to working implementation?

2.  2. Optional LLM consultation for specific design challenges

    -   Complex algorithmic decisions
    -   Data structure optimization
    -   Error handling strategies
    -   Integration approach refinement

3.  3. Specification refinement

    -   Update specifications based on reflection and consultation
    -   Add missing details discovered during reflection
    -   Resolve any internal contradictions
    -   Ensure complete coverage of identified requirements


<a id="org403ab5a"></a>

### Decision criteria for moving to Phase 3.1

-   You can confidently explain every design decision and its rationale
-   All major failure modes from Phase 1.2 are addressed in the specifications
-   You can visualize the complete data flow from input to output
-   No remaining uncertainty about fundamental architectural choices
-   The specifications feel complete enough for systematic decomposition

1.  HUMAN OUTPUT

    Final validated technical specifications ready for atomic decomposition
    
    > **Critical Time Allocation Note**: Phases 1.1 through 2.2 should consume approximately **67% of total project time**. This upfront investment in design quality dramatically reduces debugging and rework time in later phases.


<a id="orgda62028"></a>

# Phase 3: Atomic Unit Decomposition


<a id="orgdd80d9c"></a>

## 3.1 Specification Decomposition (Two-Document Approach)


<a id="org8ea04c5"></a>

### 3.1.1 Generate Decomposition Documents

1.  HUMAN INPUT TO LLM:

        I have completed technical specifications for a data science tool. I need you to break these specifications into atomic units that build incrementally and can be coded and tested one at a time.
        
        SPECIFICATIONS:
        [Copy complete technical specifications from Phase 2.1]
        
        EXISTING CODE REPOSITORIES FOR REUSE:
        [Include relevant previous project repositories, particularly highlighting reusable functions, patterns, or approaches identified in Phase 1.1]
        
        Previous Project Examples:
        - fly_behavior_analysis: [Include repository link or key code sections]
        - [Other relevant projects]
        
        Key reusable components identified:
        - [List specific functions, patterns, or modules that could be adapted from Phase 1.1 assessment]
        
        REQUIREMENTS FOR ATOMIC UNITS:
        - Each unit should perform a single, clearly defined action
        - Unit 1 must be completely standalone and testable in isolation
        - Unit 2 can depend on Unit 1 and must be testable with Unit 1 present
        - Unit 3 can depend on Units 1-2 and must be testable with Units 1-2 present
        - And so on... Unit N can depend on Units 1 through N-1
        - Each unit should be understandable to someone learning Python
        - Each unit must include specific test requirements that work with all previously completed units available
        - When possible, units should adapt/reuse existing code rather than creating from scratch
        - Clearly indicate which units involve code reuse vs. new development
        
        EXAMPLE INCREMENTAL BUILDING:
        If creating a data processing pipeline:
        - Unit 1: "Adapt load_csv_file() from fly_behavior_analysis for new data format" (reuse with modifications)
        - Unit 2: "Create new data cleaning function using validation patterns from Unit 1" (new code building on adapted foundation)
        - Unit 3: "Generate summary statistics using cleaned data from Unit 2" (can use Units 1-2)
        - Unit 4: "Adapt visualization approach from previous project for new statistics" (reuse with modifications)
        
        Each unit builds on the solid, tested foundation of previous units and leverages existing proven solutions where appropriate.
        
        OUTPUT TWO DOCUMENTS:
        
        DOCUMENT 1: PROMPT ENGINEERING GUIDE (FOR SUBSEQUENT LLM INTERACTIONS)
        For each identified unit, provide:
        - Unit ID and clear descriptive name
        - Whether this unit involves: NEW CODE, CODE ADAPTATION, or DIRECT REUSE
        - For adaptations/reuse: specific reference to existing code location
        - Precise coding prompt that includes:
          * Exact function signature
          * Input/output specifications
          * Required error handling
          * Specific unit test requirements
          * Code documentation standards
          * For reuse: specific modifications needed from original
        - Dependencies on previous units
        - Expected completion time
        
        DOCUMENT 2: PERSONAL TODO LIST (FOR HUMAN PROJECT MANAGEMENT)
        A milestone-based checklist containing:
        - Sequential list of all units in dependency order
        - Estimated time for each unit (accounting for reuse vs. new development)
        - Code reuse milestones (when to integrate adapted components)
        - Key integration points where multiple units come together
        - Testing milestones (when to run integration tests)
        - Documentation checkpoints
        
        Be systematic and thorough. Prioritize code reuse where appropriate to accelerate development while maintaining learning objectives.

2.  LLM OUTPUT

    -   **Document 1**: Prompt Engineering Guide (structured for LLM consumption)
    -   **Document 2**: Personal Todo List (structured for human project management)

3.  Phase Transition Note.

    The extensive design dialogue in this phase may warrant a clean context reset before Phase 2.2 using the Phase Transition Template.


<a id="org4b727ca"></a>

### 3.2 Decomposition Quality Control

1.  Review criteria

    -   Is Unit 1 completely standalone with no dependencies?
    -   Can each subsequent unit be coded using only previously completed units (Unit N depends only on Units 1 through N-1)?
    -   Does each unit have clear, testable success criteria that work with the incremental codebase?
    -   Are dependencies between units explicitly documented in dependency order?
    -   Do the prompts include sufficient context for quality code generation with existing foundation?
    -   Is the granularity appropriate for learning Python concepts while building incrementally?
    
    **If quality issues found**: Iterate with LLM to refine decomposition.

2.  HUMAN OUTPUT

    Validated Prompt Engineering Guide and Personal Todo List ready for development


<a id="org13a0332"></a>

# Phase 4: Systematic Code Development


<a id="orgf898574"></a>

## 4.1 Repository Setup


<a id="org154d03d"></a>

### Setup Tasks

1.  Initialize git repository with clear README
2.  Set up project structure (following your proven approach)
3.  Create environment.yml and requirements.txt
4.  Establish testing framework (pytest)
5.  Create initial documentation structure


<a id="org9814c8c"></a>

## 4.2 Per-Unit Development Workflow


<a id="orga7b40ff"></a>

### Step 1: Prompt Execution

1.  HUMAN INPUT TO LLM:

    -   Copy exact prompt from Prompt Engineering Guide for current unit
    -   For CODE ADAPTATION units: include existing code reference in prompt
    -   For DIRECT REUSE units: copy existing code and modify as specified
    -   For NEW CODE units: use standard LLM generation

2.  Workflow

    -   **LLM OUTPUT**: Generated/adapted code with tests
    -   **HUMAN ACTIVITY**: Request modifications if output doesn't match prompt specifications


<a id="org9281246"></a>

### Step 2: Code Understanding (Learning Phase)

1.  For NEW CODE or significant adaptations

    1.  HUMAN INPUT TO LLM:
    
            I received this code for [unit description]:
            
            [Paste generated/adapted code]
            
            I'm learning Python and need to understand every part. Please explain:
            1. Each function and its purpose
            2. Any Python concepts or libraries I might not know
            3. Why this approach was chosen (especially vs. the original if adapted)
            4. How the error handling works
            5. What each part of the test does
            
            Ask me questions to check my understanding. Don't move on until I can explain the code back to you.
    
    2.  Workflow
    
        -   **LLM OUTPUT**: Explanations and comprehension questions
        -   **HUMAN ACTIVITY**: Answer questions, ask for clarification

2.  For DIRECT REUSE

    Review existing code documentation and tests to ensure understanding.
    
    **Continue until**: You can explain the code confidently without reference.


<a id="org699091c"></a>

### Step 3: Integration

-   Add code to project repository
-   Update imports and dependencies
-   Ensure code follows project standards
-   Update documentation


<a id="org8f18bd0"></a>

### Step 4: Testing

-   Run unit tests for current unit (with all previously completed units available)
-   Run integration tests with all previously completed units
-   Verify new unit works correctly with existing foundation
-   If tests fail: troubleshoot systematically, document issues


<a id="org8527594"></a>

### Step 5: Optional Troubleshooting

-   **HUMAN INPUT TO LLM**: Error messages, failing test descriptions
-   **LLM OUTPUT**: Debugging assistance and suggestions
-   **HUMAN ACTIVITY**: Apply fixes, test edge cases manually, refine error handling


<a id="org44529e8"></a>

### Step 6: Version Control

-   Commit with descriptive message
-   Tag major milestones
-   Update changelog


<a id="org27a476e"></a>

### Step 7: Documentation

-   Update README with new functionality
-   Document any deviations from original specifications
-   Note lessons learned for future reference


<a id="org17c8e42"></a>

### Step 8: Progress Tracking

-   Check off unit in Personal Todo List
-   Estimate remaining time
-   Proceed to next unit


<a id="org97eed2f"></a>

## 4.3 Integration Milestones


<a id="orgf80069d"></a>

### Milestone Tasks

1.  Run full test suite
2.  Test end-to-end workflows with realistic data
3.  Validate outputs match specifications
4.  Document any discovered limitations
5.  Update project documentation


<a id="orgd149375"></a>

# Phase 5: Quality Assurance and Finalization


<a id="org2e95ad8"></a>

## 5.1 Final Integration Testing

-   Test complete pipeline with real project data
-   Validate all outputs match specification requirements
-   Perform edge case testing based on negative space map
-   Document any remaining limitations


<a id="org66ee23d"></a>

## 5.2 Documentation Finalization

-   Complete README with installation and usage instructions
-   Document all known limitations and workarounds
-   Include examples with realistic data
-   Add references to theoretical background


<a id="orgc5cc863"></a>

## 5.3 Repository Quality Standards


<a id="org1a36b4f"></a>

### Quality Checklist

-   [ ] Comprehensive README
-   [ ] All dependencies documented
-   [ ] Complete test coverage
-   [ ] Clear licensing
-   [ ] Reproducible examples
-   [ ] Version tagging


<a id="org92a40d1"></a>

# Workflow Timing Guidelines


<a id="orge522f56"></a>

## Phase Distribution

-   **Phase 1 (Bootstrap)**: 1-2 days (~25% of project time)
    -   Goal clarification: 3-6 hours
    -   Negative space mapping: 6-10 hours

-   **Phase 2 (Specifications)**: 1.5-3 days (~40% of project time)
    -   Specification brainstorming: 6-12 hours
    -   Specification iteration: 6-12 hours

> **Critical Design Investment**: Phases 1-2 should consume **~67% of total project time** to ensure robust design foundation

-   **Phase 3 (Decomposition)**: 0.5-1 day (~15% of project time)
    -   Atomic unit decomposition: 3-6 hours
    -   Quality control: 1-2 hours

-   **Phase 4 (Development)**: 1-1.5 days (~15% of project time)
    -   Per-unit development: 10-20 minutes per unit
    -   Integration milestones: 30-60 minutes each

-   **Phase 5 (Finalization)**: 0.25-0.5 day (~5% of project time)
    -   Final testing and documentation: 2-4 hours


<a id="org6ae4b7b"></a>

## Total Range

4.5-7.5 days


<a id="orga82a224"></a>

## Key Insight

Heavy upfront design investment (67% of time) dramatically reduces debugging and rework time, making total development time shorter and more predictable.


<a id="org3a62132"></a>

# Success Criteria

A successful project completion includes:

-   [X] All units pass individual tests
-   [X] Complete pipeline processes realistic data successfully
-   [X] Code is readable and well-documented
-   [X] Repository follows research-grade standards
-   [X] No blocking errors in normal usage scenarios
-   [X] Author can explain every code component confidently
-   [X] Statistical outputs meet original specifications
-   [X] Tool addresses original problem statement


<a id="org67eab4f"></a>

# Adaptation Guidelines


<a id="orgf160839"></a>

## For simpler projects

-   Compress bootstrap phase (focus on data flow failures)
-   Reduce decomposition granularity
-   Streamline documentation requirements


<a id="orgf0f3c50"></a>

## For more complex projects

-   Extend negative space mapping with additional failure scenarios
-   Add intermediate integration milestones
-   Consider prototype development before full specifications
-   Include performance testing at integration points


<a id="org2db42ce"></a>

## Learning focus adjustments

-   Increase unit granularity for unfamiliar concepts
-   Add explicit concept-learning checkpoints
-   Include additional explanation prompts for complex algorithms

> This procedure provides a systematic, scalable approach to developing research-grade data science tools while maintaining learning objectives and minimizing debugging overhead through comprehensive upfront planning.


<a id="org9bc010c"></a>

# Complete Human-LLM Workflow Summary

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">Phase</th>
<th scope="col" class="org-left">Step</th>
<th scope="col" class="org-left">Human Input</th>
<th scope="col" class="org-left">Human Activity</th>
<th scope="col" class="org-left">LLM Input</th>
<th scope="col" class="org-left">LLM Output</th>
<th scope="col" class="org-left">Human Output</th>
</tr>
</thead>
<tbody>
<tr>
<td class="org-right">1.1</td>
<td class="org-left">Goal Clarification</td>
<td class="org-left">Pen &amp; paper</td>
<td class="org-left">Handwrite, validate with colleague</td>
<td class="org-left">None</td>
<td class="org-left">None</td>
<td class="org-left">Intent Document</td>
</tr>

<tr>
<td class="org-right">1.2</td>
<td class="org-left">Negative Space</td>
<td class="org-left">Intent Document</td>
<td class="org-left">Answer questions, take notes</td>
<td class="org-left">Intent Document + context</td>
<td class="org-left">Socratic questions</td>
<td class="org-left">Failure mode notes</td>
</tr>

<tr>
<td class="org-right">1.2</td>
<td class="org-left">Final Consolidation</td>
<td class="org-left">All failure notes</td>
<td class="org-left">Create consolidated document</td>
<td class="org-left">None</td>
<td class="org-left">None</td>
<td class="org-left">Negative Space Map</td>
</tr>

<tr>
<td class="org-right">2.1</td>
<td class="org-left">Spec Brainstorming</td>
<td class="org-left">Intent + Negative Space + Reuse</td>
<td class="org-left">Answer design questions, document decisions</td>
<td class="org-left">Intent + Negative Space + Reuse</td>
<td class="org-left">Design exploration questions</td>
<td class="org-left">Draft specifications</td>
</tr>

<tr>
<td class="org-right">2.2</td>
<td class="org-left">Spec Iteration</td>
<td class="org-left">Draft specifications</td>
<td class="org-left">Deep reflection, optional LLM consultation</td>
<td class="org-left">Optional: specific design challenges</td>
<td class="org-left">Optional: design guidance</td>
<td class="org-left">Final specifications</td>
</tr>

<tr>
<td class="org-right">3.1</td>
<td class="org-left">Decomposition</td>
<td class="org-left">Final Specs + Code Repos</td>
<td class="org-left">Structure input, review output</td>
<td class="org-left">Specs + repos + requirements</td>
<td class="org-left">Prompt Guide + Todo List</td>
<td class="org-left">Quality-checked documents</td>
</tr>

<tr>
<td class="org-right">4.1-8</td>
<td class="org-left">Each Unit</td>
<td class="org-left">Prompt from Guide</td>
<td class="org-left">Execute 8-step workflow</td>
<td class="org-left">Individual prompts</td>
<td class="org-left">Code + explanations</td>
<td class="org-left">Working code units</td>
</tr>

<tr>
<td class="org-right">5</td>
<td class="org-left">Finalization</td>
<td class="org-left">All outputs</td>
<td class="org-left">Final testing &amp; documentation</td>
<td class="org-left">None (or optional assistance)</td>
<td class="org-left">None (or assistance)</td>
<td class="org-left">Research-grade repository</td>
</tr>
</tbody>
</table>


<a id="org4d4fd97"></a>

## Key Insight

The procedure alternates between deep human thinking (handwritten foundation, specification writing) and collaborative human-LLM work (Socratic questioning, code generation), ensuring both cognitive rigor and implementation efficiency.

