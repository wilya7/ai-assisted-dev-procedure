# Table of Contents

1.  [Living Document Update Prompt](#orgfc09745)
    1.  [Update Protocol](#org723d296)
2.  [Overview](#orgb7d49ac)
3.  [Human-LLM Interaction Framework](#org4254d0c)
    1.  [Clear handoff specifications for each phase](#org8f18e50)
    2.  [Key Principle](#org6230256)
4.  [Phase 1: Project Bootstrap](#org009487a)
    1.  [1.1 Goal Clarification](#org4767831)
        1.  [HUMAN ACTIVITY (No LLM involvement)](#orgce299d8)
    2.  [1.2 Negative Space Mapping (Socratic Failure Mode Analysis)](#org561eae2)
        1.  [1.2.1 Data Flow Failure Modes](#org02ae595)
        2.  [1.2.2 Assumption Violations](#org43a0922)
        3.  [1.2.3 Integration Disasters](#orgb671bac)
        4.  [1.2.4 Scale-Up Failures](#orgcb0e6a1)
5.  [Phase 2: Specification Development](#orgd5e55ac)
    1.  [2.1 Technical Specification Brainstorming (Socratic Design Dialog)](#org8c9f7a2)
        1.  [HUMAN INPUT TO LLM:](#org04fae07)
        2.  [Workflow](#org1899970)
    2.  [2.2 Specification Iteration and Validation](#org58404bf)
        1.  [Iterative refinement process](#org7d72602)
        2.  [Decision criteria for moving to Phase 3.1](#orgbea1918)
6.  [Phase 3: Atomic Unit Decomposition](#orgc0687d4)
    1.  [3.1 Specification Decomposition (Two-Document Approach)](#org297a05a)
        1.  [3.1.1 Generate Decomposition Documents](#org9d56db3)
        2.  [3.2 Decomposition Quality Control](#orgb152afc)
7.  [Phase 4: Systematic Code Development](#orgfa411ca)
    1.  [4.1 Repository Setup](#orgc3a8ecb)
        1.  [Setup Tasks](#org8f041b5)
    2.  [4.2 Per-Unit Development Workflow](#org07991cf)
        1.  [Step 1: Prompt Execution](#org8772080)
        2.  [Step 2: Code Understanding (Learning Phase)](#org01eb2be)
        3.  [Step 3: Integration](#org807604a)
        4.  [Step 4: Testing](#orgc598113)
        5.  [Step 5: Optional Troubleshooting](#orgdda6331)
        6.  [Step 6: Version Control](#org448a32c)
        7.  [Step 7: Documentation](#org3b11154)
        8.  [Step 8: Progress Tracking](#org0daaac5)
    3.  [4.3 Integration Milestones](#org2909991)
        1.  [Milestone Tasks](#orgc967d76)
8.  [Phase 5: Quality Assurance and Finalization](#orgfd2334c)
    1.  [5.1 Final Integration Testing](#orge9a2299)
    2.  [5.2 Documentation Finalization](#org9e43004)
    3.  [5.3 Repository Quality Standards](#org63f98ce)
        1.  [Quality Checklist](#orgbbe39ff)
9.  [Workflow Timing Guidelines](#orgdf5d951)
    1.  [Phase Distribution](#org7f8d176)
    2.  [Total Range](#orgae9cb18)
    3.  [Key Insight](#org44eaad2)
10. [Success Criteria](#org4fdab5b)
11. [Adaptation Guidelines](#org7737aec)
    1.  [For simpler projects](#orgb559a85)
    2.  [For more complex projects](#orgff56b5c)
    3.  [Learning focus adjustments](#orgaaa0324)
12. [Complete Human-LLM Workflow Summary](#orgdeeb054)
    1.  [Key Insight](#org5578d4d)



<a id="orgfc09745"></a>

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


<a id="org723d296"></a>

## Update Protocol

-   Test the procedure on real projects
-   Document what works and what needs improvement
-   Use the prompt above to get systematic refinements
-   Increment version number for each refinement cycle
-   Maintain the core philosophy: systematic design thinking + learning-focused implementation + research-grade quality


<a id="orgb7d49ac"></a>

# Overview

This procedure systematically develops focused, project-specific data analysis tools while maintaining research-grade quality standards. The workflow emphasizes thorough upfront planning to minimize debugging time and maximize learning value through granular, testable code units.


<a id="org4254d0c"></a>

# Human-LLM Interaction Framework


<a id="org8f18e50"></a>

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


<a id="org6230256"></a>

## Key Principle

Documents created FOR LLMs are structured for machine consumption. Documents created BY LLMs are structured for human use. Documents created by humans FOR humans prioritize clarity and decision-making.


<a id="org009487a"></a>

# Phase 1: Project Bootstrap


<a id="org4767831"></a>

## 1.1 Goal Clarification


<a id="orgce299d8"></a>

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


<a id="org561eae2"></a>

## 1.2 Negative Space Mapping (Socratic Failure Mode Analysis)

**Process**: Engage LLM as Socratic teacher to systematically explore failure modes across four dimensions:


<a id="org02ae595"></a>

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


<a id="org43a0922"></a>

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


<a id="orgb671bac"></a>

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


<a id="orgcb0e6a1"></a>

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


<a id="orgd5e55ac"></a>

# Phase 2: Specification Development


<a id="org8c9f7a2"></a>

## 2.1 Technical Specification Brainstorming (Socratic Design Dialog)


<a id="org04fae07"></a>

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


<a id="org1899970"></a>

### Workflow

-   **LLM OUTPUT**: Series of design exploration questions
-   **HUMAN ACTIVITY**: Answer questions, explore design implications, document design decisions
-   **HUMAN OUTPUT**: Draft technical specifications with rationale for each design decision

**Continue until**: You have systematically explored all major design decisions and their implications.


<a id="org58404bf"></a>

## 2.2 Specification Iteration and Validation


<a id="org7d72602"></a>

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


<a id="orgbea1918"></a>

### Decision criteria for moving to Phase 3.1

-   You can confidently explain every design decision and its rationale
-   All major failure modes from Phase 1.2 are addressed in the specifications
-   You can visualize the complete data flow from input to output
-   No remaining uncertainty about fundamental architectural choices
-   The specifications feel complete enough for systematic decomposition

1.  HUMAN OUTPUT

    Final validated technical specifications ready for atomic decomposition
    
    > **Critical Time Allocation Note**: Phases 1.1 through 2.2 should consume approximately **67% of total project time**. This upfront investment in design quality dramatically reduces debugging and rework time in later phases.


<a id="orgc0687d4"></a>

# Phase 3: Atomic Unit Decomposition


<a id="org297a05a"></a>

## 3.1 Specification Decomposition (Two-Document Approach)


<a id="org9d56db3"></a>

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


<a id="orgb152afc"></a>

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


<a id="orgfa411ca"></a>

# Phase 4: Systematic Code Development


<a id="orgc3a8ecb"></a>

## 4.1 Repository Setup


<a id="org8f041b5"></a>

### Setup Tasks

1.  Initialize git repository with clear README
2.  Set up project structure (following your proven approach)
3.  Create environment.yml and requirements.txt
4.  Establish testing framework (pytest)
5.  Create initial documentation structure


<a id="org07991cf"></a>

## 4.2 Per-Unit Development Workflow


<a id="org8772080"></a>

### Step 1: Prompt Execution

1.  HUMAN INPUT TO LLM:

    -   Copy exact prompt from Prompt Engineering Guide for current unit
    -   For CODE ADAPTATION units: include existing code reference in prompt
    -   For DIRECT REUSE units: copy existing code and modify as specified
    -   For NEW CODE units: use standard LLM generation

2.  Workflow

    -   **LLM OUTPUT**: Generated/adapted code with tests
    -   **HUMAN ACTIVITY**: Request modifications if output doesn't match prompt specifications


<a id="org01eb2be"></a>

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


<a id="org807604a"></a>

### Step 3: Integration

-   Add code to project repository
-   Update imports and dependencies
-   Ensure code follows project standards
-   Update documentation


<a id="orgc598113"></a>

### Step 4: Testing

-   Run unit tests for current unit (with all previously completed units available)
-   Run integration tests with all previously completed units
-   Verify new unit works correctly with existing foundation
-   If tests fail: troubleshoot systematically, document issues


<a id="orgdda6331"></a>

### Step 5: Optional Troubleshooting

-   **HUMAN INPUT TO LLM**: Error messages, failing test descriptions
-   **LLM OUTPUT**: Debugging assistance and suggestions
-   **HUMAN ACTIVITY**: Apply fixes, test edge cases manually, refine error handling


<a id="org448a32c"></a>

### Step 6: Version Control

-   Commit with descriptive message
-   Tag major milestones
-   Update changelog


<a id="org3b11154"></a>

### Step 7: Documentation

-   Update README with new functionality
-   Document any deviations from original specifications
-   Note lessons learned for future reference


<a id="org0daaac5"></a>

### Step 8: Progress Tracking

-   Check off unit in Personal Todo List
-   Estimate remaining time
-   Proceed to next unit


<a id="org2909991"></a>

## 4.3 Integration Milestones


<a id="orgc967d76"></a>

### Milestone Tasks

1.  Run full test suite
2.  Test end-to-end workflows with realistic data
3.  Validate outputs match specifications
4.  Document any discovered limitations
5.  Update project documentation


<a id="orgfd2334c"></a>

# Phase 5: Quality Assurance and Finalization


<a id="orge9a2299"></a>

## 5.1 Final Integration Testing

-   Test complete pipeline with real project data
-   Validate all outputs match specification requirements
-   Perform edge case testing based on negative space map
-   Document any remaining limitations


<a id="org9e43004"></a>

## 5.2 Documentation Finalization

-   Complete README with installation and usage instructions
-   Document all known limitations and workarounds
-   Include examples with realistic data
-   Add references to theoretical background


<a id="org63f98ce"></a>

## 5.3 Repository Quality Standards


<a id="orgbbe39ff"></a>

### Quality Checklist

-   [ ] Comprehensive README
-   [ ] All dependencies documented
-   [ ] Complete test coverage
-   [ ] Clear licensing
-   [ ] Reproducible examples
-   [ ] Version tagging


<a id="orgdf5d951"></a>

# Workflow Timing Guidelines


<a id="org7f8d176"></a>

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


<a id="orgae9cb18"></a>

## Total Range

4.5-7.5 days


<a id="org44eaad2"></a>

## Key Insight

Heavy upfront design investment (67% of time) dramatically reduces debugging and rework time, making total development time shorter and more predictable.


<a id="org4fdab5b"></a>

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


<a id="org7737aec"></a>

# Adaptation Guidelines


<a id="orgb559a85"></a>

## For simpler projects

-   Compress bootstrap phase (focus on data flow failures)
-   Reduce decomposition granularity
-   Streamline documentation requirements


<a id="orgff56b5c"></a>

## For more complex projects

-   Extend negative space mapping with additional failure scenarios
-   Add intermediate integration milestones
-   Consider prototype development before full specifications
-   Include performance testing at integration points


<a id="orgaaa0324"></a>

## Learning focus adjustments

-   Increase unit granularity for unfamiliar concepts
-   Add explicit concept-learning checkpoints
-   Include additional explanation prompts for complex algorithms

> This procedure provides a systematic, scalable approach to developing research-grade data science tools while maintaining learning objectives and minimizing debugging overhead through comprehensive upfront planning.


<a id="orgdeeb054"></a>

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


<a id="org5578d4d"></a>

## Key Insight

The procedure alternates between deep human thinking (handwritten foundation, specification writing) and collaborative human-LLM work (Socratic questioning, code generation), ensuring both cognitive rigor and implementation efficiency.

