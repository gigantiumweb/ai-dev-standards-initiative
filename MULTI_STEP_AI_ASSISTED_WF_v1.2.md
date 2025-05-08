--- START OF FILE [MULTI_STEP_AI_ASSISTED_WF_v1.2.md] ---
# **Framework: Multi-Step AI-Assisted Workflow (MAIA-WF) - v1.2**

**Authors:** Philippe Sthely
**Date:** [05/08/2025]
**Version:** 1.2

**1. Introduction & Purpose**

The Multi-Step AI-Assisted Workflow (MAIA-WF) framework provides a structured methodology for tackling complex tasks through a series of well-defined steps, leveraging the collaborative strengths of a human User and an AI assistant (e.g., `Catalyst`). It promotes clarity, iterative refinement, detailed record-keeping, and efficient progress, especially in resource-constrained environments or when dealing with novel problems. The framework also supports hierarchical decomposition, allowing complex steps within a MAIA-Workflow to be executed as distinct Sub-MAIA-Workflows, further enhancing manageability for large-scale tasks.

This framework is designed to be adaptable for various tasks, including but not limited to:
*   Feature design and specification
*   Problem decomposition and analysis
*   Strategic planning
*   Content creation and refinement
*   Decision-making processes
*   Project implementation phases (where each phase can be a sub-workflow)

**2. Core Philosophy**

*   **Structured Collaboration:** Breaks down complexity into manageable stages, each with clear inputs, actions, and outputs.
*   **Iterative Refinement:** Emphasizes review and feedback loops between the User and AI at each step.
*   **Role-Based AI Interaction:** The AI assistant can adopt different "personas" or "roles" tailored to the specific needs of each step (e.g., `Analyst`, `Designer`, `Planner`, `Reviewer`).
*   **Clear Human Oversight:** The User acts as the orchestrator, strategic decision-maker, reviewer, and final approver.
*   **Documentation by Design:** The process naturally generates a trail of decisions, inputs, and outputs, facilitating project tracking and knowledge retention.
*   **Project Continuity:** Incorporates mechanisms for consolidating and exporting project state to ensure efficient context transfer between work sessions.
*   **Hierarchical Structure:** Allows complex steps within a MAIA-Workflow to be executed as distinct Sub-MAIA-Workflows, promoting deeper structured collaboration and robust context management for large-scale or highly detailed tasks.

**3. Key Components of a MAIA-Workflow**

Each MAIA-Workflow instance typically consists of:

*   **3.1. Workflow Definition:**
    *   **Overall Goal:** What the workflow aims to achieve.
    *   **Sequence of Steps:** An ordered list of distinct stages.
*   **3.2. For Each Step (excluding the final Project State Export step, which has a specific structure):**
    *   **Step Name/Number:** Clear identifier.
    *   **Execution Mode (Optional, Default: Standard):** Indicates if the step is executed directly or as a Sub-MAIA-Workflow. Values: "Standard", "Sub-MAIA-Workflow".
    *   **Responsible Roles:**
        *   **AI Persona/Role:** The specific hat the AI wears for this step (e.g., `Catalyst` as `BusinessAnalyst`). If Execution Mode is "Sub-MAIA-Workflow", these roles may pertain to the oversight or initiation of the sub-workflow.
        *   **User Role:** The primary function of the User in this step (e.g., `StrategicReviewer`, `FeedbackProvider`).
    *   **Inputs:** What information or artifacts are required to start this step (often the output of the previous step).
    *   **AI Actions:** The specific tasks to be performed by the AI. If Execution Mode is "Sub-MAIA-Workflow", a primary AI action is to collaboratively define the Sub-MAIA-Workflow.
    *   **User Actions:** The specific tasks to be performed by the User (e.g., review, feedback, approval). If Execution Mode is "Sub-MAIA-Workflow", a primary User action is to approve the definition of, and then orchestrate/participate in, the Sub-MAIA-Workflow.
    *   **Outputs:** The tangible deliverables or decisions resulting from this step. If Execution Mode is "Sub-MAIA-Workflow", the outputs will primarily be the consolidated deliverables and Export Package List from the completed Sub-MAIA-Workflow.
    *   **Completion Criteria:** How to determine if the step is successfully completed (often User approval of the output). If Execution Mode is "Sub-MAIA-Workflow", completion criteria involve the successful execution and approval of the entire Sub-MAIA-Workflow.

**4. General MAIA-Workflow Process**

1.  **Define the Workflow:**
    *   User and AI collaboratively define the overall goal and the sequence of steps, including roles, inputs, actions, and outputs for each step, culminating in the "Project State Consolidation & Export" step (see Section 8).
2.  **Execute Step-by-Step:**
    *   Begin with Step 1.
    *   **For a "Standard" Execution Mode step:**
        *   The AI (in its defined persona for the step) processes the inputs and performs its designated actions, generating a draft output.
        *   The User reviews the AI's output, provides feedback, asks for clarifications, or requests revisions.
        *   This AI generation -> User review -> AI revision loop continues within the step until the User approves the output for that step.
        *   The approved output of one step becomes the primary input for the next.
    *   **For a "Sub-MAIA-Workflow" Execution Mode step:**
        *   The User and AI (in their roles for overseeing the sub-workflow) collaboratively define the Sub-MAIA-Workflow. This definition includes its own Overall Goal, Sequence of Steps, Roles, Inputs, Actions, Outputs, and Completion Criteria for each of its internal steps, including its own final "Project State Consolidation & Export" step.
        *   The defined Sub-MAIA-Workflow is then executed according to this framework (recursively, if needed, though deep nesting should be used judiciously).
        *   Upon successful completion and approval of the Sub-MAIA-Workflow (including its state export), its key deliverables and Export Package List become the primary outputs of the current step in the parent workflow.
        *   The parent workflow then proceeds to its next step.
3.  **Branching & Iteration (Now potentially formalized as Sub-MAIA-Workflows):**
    *   If a step involves exploring multiple options or requires a deep dive into a sub-problem, the User can initiate a "branch."
    *   This "branch" can be handled as an ad-hoc series of interactions within the current step or, for more significant sub-problems, be formally defined and executed as a Sub-MAIA-Workflow.
    *   The outcome of the branch/sub-workflow is summarized and brought back to the main workflow step.
4.  **Documentation & Record Keeping (Ongoing):**
    *   The User is responsible for saving key inputs, AI outputs, User feedback, and final approved outputs for each step. This is formalized in the final "Project State Consolidation & Export" step of both parent and any Sub-MAIA-Workflows.
5.  **Workflow Completion:**
    *   The workflow (and any of its sub-workflows) is complete when all defined steps, including the "Project State Consolidation & Export" step, have been successfully executed and their outputs approved, leading to the achievement of the overall goal and a well-documented project state.

**5. Example Workflow Structure (Template)**

**Workflow Name:** [Name of the Overall Workflow]

*   **Overall Goal:** [Describe the final objective]
*   **Prerequisites/Global Inputs:** [Any information needed before starting Step 1]

---
**Step 1: [Name of Step 1]**
*   **Execution Mode:** Standard (or Sub-MAIA-Workflow)
*   **AI Persona/Role:** `Catalyst` as `[SpecificRoleForStep1]`
*   **User Role:** `[SpecificUserRoleForStep1]`
*   **Inputs:** ...
*   **AI Actions:** ...
*   **User Actions:** ...
*   **Outputs:** ...
*   **Completion Criteria:** User approves ...

---
**(Example of a step executed as a Sub-MAIA-Workflow)**
**Step 2: [Name of Step 2, e.g., Detailed Design of Feature X]**
*   **Execution Mode:** Sub-MAIA-Workflow
*   **Sub-MAIA-Workflow Name:** [e.g., Feature X Design Sub-WF]
*   **AI Persona/Role (for overseeing Sub-WF):** `Catalyst` as `DesignLead`
*   **User Role (for overseeing Sub-WF):** `ProductManager`
*   **Inputs (to this parent step, to inform Sub-WF definition):** Approved requirements from Step 1, relevant architectural documents.
*   **AI Actions (for this parent step):**
    1.  Collaboratively define the "[Feature X Design Sub-WF]" with the User. This sub-workflow will have its own goal (e.g., "Produce detailed design specifications and mockups for Feature X") and its own internal steps (e.g., "Define User Stories for Feature X", "Create Wireframes", "Develop High-Fidelity Mockups", "Technical Feasibility Review", "Feature X Design Sub-WF: State Export").
*   **User Actions (for this parent step):**
    1.  Collaborate on and approve the definition of "[Feature X Design Sub-WF]".
    2.  Initiate, orchestrate, and participate in the execution of the "[Feature X Design Sub-WF]" according to its defined steps.
*   **Outputs (of this parent step):** The "Export Package List" and key deliverables (e.g., approved design document, mockups) from the completed "[Feature X Design Sub-WF]".
*   **Completion Criteria (for this parent step):** User confirms satisfactory completion of the "[Feature X Design Sub-WF]" and approves its outputs.
---
*(...Continue for all intermediate steps...)*
---
**Final Step: Project State Consolidation & Export** (See Section 8 for detailed structure)
*   **AI Persona/Role:** `Catalyst` as `KnowledgeManager`
*   **User Role:** `ProjectArchivist`
*   **Inputs:** All outputs from preceding steps (including outputs from any Sub-MAIA-Workflows), current project documents, list of key decisions.
*   **AI Actions:** Identify changes, draft updates for documents (or specific sections), consolidate outputs, generate summary (optional), prepare export package list.
*   **User Actions:** Review AI suggestions, manually integrate updates into master documents, verify package list, save all artifacts, confirm state export.
*   **Outputs:** Updated project documents (updated by User), new artifacts, definitive export package list.
*   **Completion Criteria:** User confirms project state is fully updated and saved.

**6. Benefits of MAIA-WF**

*   **Clarity & Focus:** Each step has a defined purpose.
*   **Improved Output Quality:** Iterative review leads to robust outcomes.
*   **Efficiency:** Reduces wasted effort by ensuring alignment.
*   **Knowledge Capture:** Inherently documents rationale and evolution.
*   **Adaptability:** Tailorable to various complex tasks.
*   **Enhanced Human-AI Synergy:** Leverages distinct strengths.
*   **Manages AI Limitations:** Mitigates risks through structured interaction.
*   **Improved Session Continuity:** Formalized state export streamlines transfer between sessions.
*   **Scalability for Complexity:** Manages highly complex projects effectively through hierarchical workflow decomposition using Sub-MAIA-Workflows.

**7. Considerations & Best Practices**

*   **Clear Prompting:** User prompts should be contextual and specific.
*   **Context Management:** User may need to remind AI of prior context; branching helps. Sub-MAIA-Workflows help encapsulate context for sub-tasks, but clear input definition from parent to child workflow is essential.
*   **Persona Consistency:** AI should maintain designated persona per step.
*   **Flexibility:** Allow for minor deviations if needed.
*   **User as Orchestrator:** User drives pace, transitions, and quality control, especially when managing Sub-MAIA-Workflows.
*   **Start Simple:** Begin with simpler workflows and add complexity (including Sub-MAIA-Workflows) as needed.
*   **Regular State Export:** For long projects, consider running the "Project State Consolidation & Export" step periodically, not just at the very end of a massive workflow. This applies to both parent and Sub-MAIA-Workflows.
*   **Judicious Use of Sub-MAIA-Workflows:** Only use sub-workflows when a step's complexity genuinely warrants a full multi-step breakdown. Over-nesting can create unnecessary overhead. Consider the granularity needed for tracking and documentation.

**8. Workflow Completion & Project State Export**

*   **8.1. Purpose:** To ensure that upon completion of a MAIA-Workflow (or a Sub-MAIA-Workflow, or at the end of a significant work session applying the MAIA-WF), the key outputs, decisions, and updated project documents are consolidated and prepared for easy transfer to a new session or for archival. This facilitates continuity and efficient context restoration.
*   **8.2. Standard "Project State Consolidation & Export" Step Structure:**
    This step should typically be the final step of any MAIA-Workflow instance (parent or sub), or a step initiated by the User at the end of a productive session.

    **Step Name:** Project State Consolidation & Export
    *   **AI Persona/Role:** `Catalyst` (or other AI) as `KnowledgeManager` or `DocumentationSynthesizer`
    *   **User Role:** `ProjectArchivist` & `Reviewer`
    *   **Inputs:**
        *   All outputs from the preceding steps of the current MAIA-Workflow instance (or sub-instance).
        *   The current versions of core project documents (e.g., Project Specification Document, design documents, MAIA-WF framework itself if updated).
        *   A list of key decisions or changes made during the session/workflow (can be provided by User or identified by AI).
    *   **AI Actions:**
        1.  **Identify Key Changes:** Based on the workflow outputs and User input, identify the core project documents that have been implicitly or explicitly updated and pinpoint the specific sections requiring modification.
        2.  **Draft Updates for Document Sections:** For each identified section requiring changes, draft the specific revised textual content for *that section*. Clearly indicate which document and section the drafted update pertains to.
        3.  **Consolidate Workflow Outputs:** List all significant new deliverables, diagrams, code snippets, or design choices generated during the workflow that may not be directly integrated into existing documents but should be archived as standalone artifacts.
        4.  **Generate Session/Workflow Summary (Optional, User-requested):** Create a brief summary of the workflow's main achievements, key decisions made, and any outstanding action items.
        5.  **Prepare Export Package List:** Compile a clear, itemized list of:
            *   The core project documents that require User integration of the drafted section updates (specifying which documents and sections).
            *   Any new, standalone artifact files created during the workflow.
            This list represents the "Export Package" the User needs to manage.
    *   **User Actions:**
        1.  Review the AI's drafted section updates and the list of identified changes.
        2.  Manually integrate these drafted updates into the master project documents, editing and refining as necessary to ensure accuracy and preserve overall document integrity.
        3.  Verify the completeness and accuracy of the "Export Package List."
        4.  Securely save all updated master documents and new standalone artifacts as per the Export Package list (e.g., commit to Git with appropriate messages, save to designated cloud storage).
        5.  Confirm to the AI that the project state has been successfully exported and saved.
    *   **Outputs:**
        *   A set of updated, versioned core project documents (physically updated and saved by the User based on AI's drafted sections).
        *   Any new artifacts created during the workflow (saved by the User).
        *   A final "Export Package List" (provided by AI, confirmed by User) that serves as a manifest for what was saved.
    *   **Completion Criteria:** User confirms all relevant project documents are updated via manual integration of AI-drafted sections and saved according to the Export Package List, and the project state is ready for a new session.

*   **8.3. Benefits for Session Management:**
    *   **Systematic Handover:** Provides a structured way to "close" a session and prepare for the next.
    *   **Reduced Context Re-entry Effort:** The "Export Package" becomes the definitive set of documents to load in a new session, ensuring the AI starts with the latest, most relevant information.
    *   **Version Control Encouragement:** Explicitly listing updated documents encourages saving and versioning.
    *   **Clarity on Current State:** Both User and AI have a clear understanding of what constitutes the "current state" at the end of a workflow.

**9. Applicability to `Project Gnomon` and Beyond**

This MAIA-WF framework (v1.2) has been instrumental in the initial design phases of `Project Gnomon`. It is intended to be:
*   A core methodology for the ongoing development of `Project Gnomon` by the User and `Catalyst`.
*   Potentially a concept or feature integrated into `Project Gnomon` itself, to guide its users in their own AI-assisted development tasks.
*   A generalizable framework that the User can adapt for other projects or complex problem-solving endeavors involving AI collaboration.
--- END OF FILE [MULTI_STEP_AI_ASSISTED_WF_v1.2.md] ---
