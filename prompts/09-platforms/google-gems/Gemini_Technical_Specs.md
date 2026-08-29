# Gemini_Technical_Specs.md

> **یادداشت مخزن:** نالج بیس شماره ۵ جم [the-architect-gem.md](the-architect-gem.md) — اینستراکشنز جم برای «بررسی امکان‌پذیری فنی و محدودیت‌ها» همیشه به همین نام ارجاع می‌دهد (سقف ۱۰ فایل نالج بیس، اندازه context window، قابلیت‌های نسخه‌های مدل). تبدیل‌شده عیناً از نسخه DOCX «Gemini_Technical_Specs.docx».

---

## 1. Executive Summary and Strategic Architectural Vision

The advent of the Gemini 3 model family in late 2025 represents a fundamental inflection point in the trajectory of artificial intelligence, transitioning the industry from the era of probabilistic text generation to the age of deliberative reasoning and agentic autonomy. This document serves as the definitive technical reference and architectural framework for "The Architect," a specialized expert system designed to leverage the capabilities of Gemini 3. "The Architect" is not merely a conversational interface; it is conceived as a "System 2" cognitive engine capable of autonomous software architecture, complex systems engineering, and multimodal analysis. To realize this vision, this report provides an exhaustive analysis of the Gemini 3 ecosystem, detailing its technical specifications, cognitive mechanics, operational constraints, and integration protocols.

The Gemini 3 architecture, specifically the gemini-3-pro-preview and gemini-3-flash-preview variants, introduces a suite of capabilities that are critical for high-fidelity architectural tasks. These include a massive 1-million-token context window that allows for the ingestion of entire repositories, a native multimodal understanding that transcends text to include "Vibe Coding" (spatial-visual reasoning), and a formalized cognitive architecture governed by "Thinking Levels" and "Thought Signatures".1 Unlike previous generations of large language models (LLMs) that relied on heuristic approximations, Gemini 3 exposes its reasoning process as a configurable hyperparameter, allowing developers to trade latency for logical depth—a feature indispensable for the rigorous demands of system architecture.

This report is structured to function as the foundational "Knowledge Source" for The Architect. It synthesizes data from technical documentation, release notes, and empirical benchmarks to establish the operational boundaries within which The Architect must function. It addresses the critical transition from "System 1" (fast, intuitive) to "System 2" (slow, deliberative) thinking, analyzing how the thinking_level parameter influences architectural decision-making. Furthermore, it provides a granular analysis of the model's multimodal signal processing capabilities, defining the physics of tokenization for audio and video inputs to optimize the utilization of the context window. By codifying these specifications, this document ensures that The Architect operates with full awareness of its own capabilities and limitations, thereby maximizing its efficacy as an autonomous engineering agent.

## 2. Model Family Taxonomy and Comparative Architecture

The Gemini 3 ecosystem is not a monolith but a tiered hierarchy of specialized compute engines, each optimized for specific dimensions of the architectural workflow. Understanding the distinct roles and capabilities of each model variant is essential for orchestrating complex agentic workflows where tasks are routed to the most appropriate cognitive resource.

### 2.1 The Gemini 3 Pro Engine (gemini-3-pro-preview)

Released on November 18, 2025, the gemini-3-pro-preview stands as the flagship reasoning engine of the family.1 It is engineered to define the state-of-the-art in complex, multi-step reasoning, making it the primary "cortex" for The Architect's most demanding tasks. This model is not designed for speed; it is designed for depth. It excels in scenarios requiring "deep architectural analysis," where the agent must navigate ambiguous requirements, resolve conflicting dependencies, and formulate long-horizon implementation plans.3

The core competency of Gemini 3 Pro lies in its default "High" thinking level. Unlike standard LLMs that generate tokens immediately upon receiving a prompt, Gemini 3 Pro engages in a dynamic computation path, exploring multiple logical branches and verifying intermediate steps before committing to an output. This "deliberative latency" is a feature, not a bug, ensuring that the generated architectural schematics or refactoring plans are logically sound and structurally consistent. For The Architect, this model is the designated engine for final system validation, security audits of large codebases, and the synthesis of "Constitutional" documentation that governs project standards.

### 2.2 The Gemini 3 Flash Engine (gemini-3-flash-preview)

Following the Pro release, gemini-3-flash-preview was launched on December 17, 2025, introducing a paradigm of "frontier-class performance" at a fraction of the cost and latency.1 It is critical to correct the misconception that "Flash" implies a "lite" or "distilled" model in the traditional sense. In the Gemini 3 era, Flash represents a highly optimized reasoning engine capable of outperforming previous generation flagship models (such as Gemini 1.5 Pro) on standard benchmarks while delivering the throughput required for real-time applications.2

For The Architect, Gemini 3 Flash serves as the high-efficiency workhorse. It is optimized for "high-frequency agentic workflows," such as iterative code generation, real-time syntax checking, and rapid documentation retrieval. A distinguishing feature of the Flash variant is its support for a wider spectrum of discrete thinking levels, including a "Minimal" mode and a "Medium" mode, which are not available or behave differently in the Pro variant.3 This granularity allows The Architect to dynamically adjust its cognitive load—utilizing Flash for the bulk of implementation tasks while reserving Pro for high-stakes decision-making.

### 2.3 The Visual Specialist (gemini-3-pro-image-preview)

While The Architect is primarily a systems engineer, the gemini-3-pro-image-preview model, released on November 20, 2025, plays a crucial niche role.1 This model is specialized for the generation and editing of high-fidelity visual assets. In the context of system architecture, this capability is leveraged for UI/UX wireframing and the generation of visual architectural diagrams. It represents a decoupled reasoning path where visual spatial logic is prioritized over textual semantic logic.

### 2.4 Context Window Physics and State Management

The unifying feature across the Gemini 3 family is the massive 1-million-token context window. This architectural specification fundamentally alters the strategy for state management within The Architect. In previous architectures, developers were forced to implement complex "Retrieval Augmented Generation" (RAG) pipelines to chunk and retrieve relevant information. With a 1-million-token window, The Architect can hold approximately 1,500 pages of dense technical text, 30,000 lines of code, or over 8 hours of audio in its active working memory.5

This capability enables "Whole-Codebase Awareness." Instead of retrieving isolated snippets of code, The Architect can ingest an entire mid-sized software repository, allowing it to trace variable states and function calls across disparate files without losing context. This eliminates a significant class of hallucinations related to "missing context" and allows for holistic refactoring that respects the global state of the application. However, this massive input capacity stands in sharp contrast to the output limit. While the input is 1 million tokens, the output generation is capped at 64,000 tokens.6 This asymmetry dictates a specific operational pattern: The Architect can read a library, but it cannot rewrite the library in a single pass. It must instead function iteratively, generating code in modular chunks or outputting "diffs" to be applied by an external system.

The "Knowledge Cutoff" for the Gemini 3 family is established as January 2025.3 This implies that The Architect possesses native knowledge of all software libraries, frameworks, and architectural patterns published prior to this date. For any technology released after January 2025, The Architect relies entirely on "in-context learning"—meaning the relevant documentation must be supplied within the prompt or the Knowledge Base files to bridge the knowledge gap.

## 3. Cognitive Architecture: The Reasoning Engine

Gemini 3 introduces a formalized "cognitive architecture" that exposes the model's internal reasoning process to the developer. This is the most significant divergence from previous LLM generations and is critical for the reliable operation of The Architect. This architecture allows for the calibration of "System 1" (fast, intuitive) versus "System 2" (slow, deliberative) thinking via the thinking_level parameter and the management of agentic state via "Thought Signatures."

### 3.1 Thinking Levels: Calibrating Cognitive Load

The thinking_level parameter acts as a throttle for the model's reasoning depth, allowing The Architect to balance latency, cost, and logical rigor based on the specific requirements of the task.3

#### 3.1.1 High Level (Default for Pro)

When set to "High," the model maximizes reasoning depth. This is the default behavior for gemini-3-pro. In this mode, the model engages in a hidden, multi-step internal monologue before emitting the first token. It explores multiple logical paths, verifies assumptions, and self-corrects potential errors. This mode is non-negotiable for critical architectural tasks such as designing database schemas, analyzing security vulnerabilities, or refactoring core system logic. The trade-off is higher latency (time-to-first-token) and increased token consumption, but the result is a significantly higher probability of correctness in complex scenarios.3

#### 3.1.2 Medium Level (Flash Only)

The "Medium" level is exclusive to the Flash variant and represents a balanced mode suitable for standard coding tasks and documentation generation. It provides a "Goldilocks" zone where the model performs necessary sanity checks without the exhaustive exploration of the High mode. For The Architect's daily coding tasks—such as writing unit tests or implementing standard API endpoints—this level offers the optimal balance of speed and reliability.8

#### 3.1.3 Low Level

The "Low" level constrains the model's thinking to minimize latency. This mode is appropriate for tasks where the logic is linear and unambiguous, such as simple instruction following, data extraction from structured text, or summarization of meeting notes. In this mode, The Architect functions closer to a traditional generative model, relying on pattern matching rather than deep reasoning.9

#### 3.1.4 Minimal Level (Flash Only)

The "Minimal" level matches the "no thinking" behavior of legacy models. It is essential for high-throughput interfaces where immediacy is prioritized over depth, such as a chat interface for quick Q&A. However, even in "Minimal" mode, Gemini 3 Flash maintains a baseline of agentic awareness and strictly requires the circulation of Thought Signatures to maintain state consistency.3 Using this mode for complex architectural reasoning is discouraged, as it increases the risk of hallucination and logical drift.

### 3.2 Thought Signatures: The Cryptographic State Mechanism

Thought Signatures represent a profound architectural innovation in Gemini 3, specifically designed for agentic workflows. They solve the "statelessness" problem of RESTful LLM interactions by encoding the model's internal reasoning state into an opaque, encrypted token sequence.10

#### 3.2.1 The Mechanics of State Preservation

In a multi-turn agentic workflow, The Architect typically follows a loop: Analyze -> Decide -> Act (Tool Call) -> Observe (Tool Result) -> React. In previous models, the "Reasoning" (Why did I call this tool?) was often lost between the "Act" and "React" phases because the API is stateless. The model would see that a tool was called but might forget the broader context or the specific hypothesis it was testing.

Gemini 3 enforces continuity through Thought Signatures. When The Architect decides to call a function (e.g., search_codebase), it emits two distinct outputs: the functionCall object and a thought_signature. This signature contains the encrypted reasoning trace—the "why" and "what next" of the agent's thought process.11

#### 3.2.2 The Protocol of Agency

The critical operational protocol for The Architect involves the strict handling of these signatures. When the system executes the tool and receives a result, it must pass both the tool's output and the original thought_signature back to the model in the subsequent request. This allows the model to "decrypt" its previous state and resume its train of thought with perfect fidelity.12

Critical Constraint: The Gemini 3 API enforces strict validation on Thought Signatures. If a functionResponse is sent back to the model without the corresponding thought_signature from the previous turn, the API will reject the request with a 400 Bad Request error.3 This makes the capture and recirculation of thought signatures a mandatory implementation detail for any custom client or script driving The Architect. It effectively binds the agent's actions to its reasoning, preventing the "disconnect" often observed in older agents where they get stuck in loops or lose track of their objective.

## 4. Knowledge Base Infrastructure and "Gem" Mechanics

The "Gem" infrastructure provides the persistent identity and long-term memory layer for The Architect. While the context window handles active, short-term working memory, the Knowledge Base serves as the repository for static, foundational truths—the "Constitution" of the agent. Configuring this layer requires navigating specific constraints regarding file counts and integration methods.

### 4.1 The 10-File Limit Constraint and Consolidation Strategy

A defining constraint of the Gem architecture is the strict limit of 10 files per Gem Knowledge Base.13 This limitation is frequently misunderstood as a capacity bottleneck, but given the 1-million-token context window, it is more accurately viewed as a "file handle" limit. The total volume of data is less restricted than the number of distinct artifacts.

For The Architect to function effectively, this constraint necessitates a strategy of Knowledge Consolidation. Instead of uploading fifty individual source code files or twenty separate policy documents, the knowledge base must be structured into consolidated "Mega-Documents." For example, all coding style guides, linting rules, and architectural patterns should be merged into a single THE_ARCHITECT_CONSTITUTION.pdf or GEMINI.md. Similarly, disparate API documentation should be concatenated into a unified reference file. This approach allows The Architect to access a vast breadth of information while consuming only a single "file slot" of the ten available.15

### 4.2 Dynamic Knowledge via Google Drive Integration

A powerful capability available to The Architect is the dynamic linking of Google Drive files. Unlike static uploads (PDF/DOCX) which represent a snapshot of information at the time of upload, Google Docs and Sheets linked from Drive maintain a live connection.13

When a Google Doc is referenced in the Knowledge Base, The Architect always accesses the most recent version of that file. This mechanism enables "Living Documentation." For instance, the human engineering team can maintain a "Current Sprint Objectives" Google Doc. As priorities change and the doc is updated by humans, The Architect automatically aligns with the new objectives in its next interaction without needing to be reconfigured or rebuilt. This is the preferred method for maintaining volatile information such as project roadmaps, active task lists, or evolving API specs.

### 4.3 Supported File Formats and Parsing Fidelity

The Architect's ability to ingest knowledge is contingent on the fidelity of the file parsing. Gemini 3 supports a broad array of formats, but their processing varies.14

- Document Formats: PDF, DOC, DOCX, TXT, RTF, DOT, DOTX, HWP, HWPX.
  - Insight: PDFs are processed with "layout fidelity," meaning the model uses its vision capabilities to understand the spatial arrangement of text and images. This is critical for ingesting architectural diagrams, flowcharts, or UML diagrams embedded in specifications. Text-only parsers often garble such visual information, but Gemini 3 preserves the semantic relationships defined by the layout.17
- Data Formats: XLS, XLSX, CSV, TSV, Google Sheets.
  - Insight: While supported, complex spreadsheets with massive dimension can be truncated. For massive datasets, it is architecturally sounder to provide a summary or a schema definition and allow The Architect to use a data analysis tool, rather than attempting to ingest millions of raw cells directly into the context window.

### 4.4 System Instructions: The Persona Definition

The System Instructions form the "personality" and operational constraints of The Architect. While there is no officially documented character limit for these instructions, empirical evidence suggests the model can handle extremely dense instruction sets—up to 17 pages of documentation—without degradation, provided they fit within the overall token budget.18

To maximize efficacy, the System Instructions should follow a "Lego-Step-by-Step" prompting strategy.19 Instructions should be granular, action-oriented, and explicitly define protocols for ambiguity resolution. Furthermore, a best practice for The Architect is to define a GEMINI.md file within the Knowledge Base that acts as the "Constitution" or "Manifesto." The System Instructions should then be kept lightweight, primarily serving to reference this Constitution (e.g., "You are The Architect. Always adhere to the principles defined in GEMINI.md"). This separation of concerns—keeping behavior in the prompt and rules in the file—improves maintainability and reduces token overhead in every turn.20

## 5. Multimodal Signal Processing and Tokenization Physics

The Architect is not limited to textual reasoning. Gemini 3's native multimodal capabilities allow it to reason over architectural diagrams, UI mockups (images), and technical walkthroughs (video/audio) with the same fluency as code. Understanding the "physics" of how these modalities are converted into tokens is vital for managing the 1-million-token budget effectively.

### 5.1 Tokenization Rates and Capacity Planning

Gemini 3 utilizes specific tokenization rates for non-text modalities. These rates are fixed and deterministic, allowing for precise capacity planning.21

| Modality | Tokenization Rate | Capacity in 1M Window | Architectural Implication |
|---|---|---|---|
| Audio | 32 tokens/second | ~8.4 - 9.5 hours | Highly efficient. Allows ingestion of full-day workshops or multiple sprint planning meetings. |
| Video | 263 tokens/second | ~1 hour | Data-heavy. Video includes audio and visual frames. Fills the context window rapidly. |
| Images | 258 tokens/image | ~3,800 images | Fixed cost for standard res. Larger images are tiled (768x768), increasing cost. |
| Text | ~1 token / 4 chars | ~1,500 pages | Standard BPE tokenization. The baseline for code and documentation. |

### 5.2 Audio Processing: The Meeting Synthesizer

The tokenization rate of 32 tokens per second for audio is exceptionally efficient.21 One hour of audio consumes approximately 115,200 tokens. This capability allows The Architect to "listen" to nearly a full work-day (approx. 8.5 hours) of continuous engineering discussions, sprint planning meetings, or architectural reviews in a single prompt.

This creates a capability unmatched by text-only models that rely on transcripts. Transcripts often contain filler words, timestamps, and speaker labels that bloat the token count significantly. By ingesting the raw audio, Gemini 3 processes the phonetic and prosodic information directly, often resulting in higher fidelity understanding of nuance and intent with lower token consumption. For The Architect, this means it can function as a "Scribe," attending meetings and synthesizing a unified design document from the verbal chaos of a brainstorming session.

### 5.3 Video Processing: Deep Visual Context

Video processing is significantly more expensive at 263 tokens per second.21 A single hour of video consumes approximately 946,800 tokens, effectively saturating the entire 1-million-token context window. This creates a binary choice for the user: The Architect can possess "Deep Visual Context" (e.g., a 1-hour screen recording of a bug reproduction) OR "Deep Code Context" (a massive repository), but not both simultaneously in a single turn.

Consequently, video uploads should be reserved for high-value visual tasks, such as analyzing a complex UI bug that involves animation timings or reviewing a user flow that is difficult to describe in text. For general knowledge transfer, audio or text remains the more token-efficient medium.

### 5.4 File Upload Limits in Active Interaction

While the Gem Knowledge Base is limited to 10 files, the active interaction limits (what the user uploads during a chat) act as the variable input stream.22

- Files per Prompt: Up to 10 files can be attached to a single chat message.
- Video Size: Maximum 2 GB per video file.
- Code Repositories: The Architect supports the direct upload of a ZIP file or a GitHub link containing up to 5,000 files or 100 MB of data.17 When a ZIP is uploaded, Gemini 3 expands it into a virtual file system within its context window, preserving the directory structure. This allows The Architect to understand "import" relationships—knowing that utils.js is in the lib/ folder—which is essential for accurate code generation and refactoring.

Operational Warning: For repositories exceeding 100MB or 5,000 files, the upload will fail. A "Pre-processing" strategy is required, where a script (git archive or similar) is used to create a "clean" ZIP that excludes binary assets (images, compiled binaries, node_modules) to keep the payload within the 100MB limit while maximizing the density of source code.17

## 6. Agentic Capabilities and "Vibe Coding"

Gemini 3 is explicitly marketed with "Agentic Coding" and "Vibe Coding" capabilities, representing a shift from passive code generation to active, spatially-aware engineering.

### 6.1 Agentic Coding: The Autonomous Loop

"Agentic Coding" refers to The Architect's ability to utilize tools to explore and verify before answering. This is powered by the "High" thinking level and Thought Signatures.

- Repository Navigation: Unlike previous models that guessed at file structures, Gemini 3 can actively "search" the virtual file system of an uploaded repo to find definitions and references.
- Iterative Correction: The model is capable of "Self-Correction." If The Architect generates code that fails a hypothetical check (simulated in its internal monologue via Thinking Mode), it can revise the code before outputting it. In an integrated environment (like Gemini Code Assist), it can even run the code, observe the error, and fix it autonomously using the Thought Signature loop.24
- Semantic Understanding: It understands the "intent" of a codebase, not just the syntax. It can infer that a variable name is_authenticated implies a security context, triggering higher scrutiny in its logic.

### 6.2 Vibe Coding: Spatial and Visual Reasoning

"Vibe Coding" is a novel term introduced with Gemini 3 to describe its enhanced spatial and visual reasoning applied to code generation.1 Traditional LLMs treat code as text; they do not "see" the output. Gemini 3, through its multimodal training, understands the layout and visual output implications of the code it writes.

- Mechanism: If prompted to "Build a 3D Voxel simulation of the Golden Gate Bridge" or "Create a dashboard with a brutalist aesthetic," Gemini 3 understands the spatial coordinates (x, y, z), the CSS flexbox properties, and the visual geometry required to achieve that "look." It connects the code (syntax) to the vibe (visual outcome).
- Application for The Architect: This is critical for Front-End architecture. The Architect can ingest a screenshot of a UI design (a "Vibe") and generate React/CSS code that accurately reflects the spacing, alignment, visual hierarchy, and padding of the design. This significantly outperforms text-only models, which often generate code that is syntactically correct but visually broken (misaligned elements, wrong colors). "Vibe Coding" ensures that The Architect serves not just as a logic engineer, but as a UI implementation specialist.24

## 7. Operational Constraints, Limitations, and Mitigation Strategies

Despite its advanced capabilities, Gemini 3 operates within strict physical and logical boundaries. A nuanced understanding of these limits is required to prevent system failures and optimize performance.

### 7.1 The Output Bottleneck (Input/Output Asymmetry)

The most significant operational constraint for The Architect is the asymmetry between its input and output capacities.

- Input: 1,048,576 tokens (The Library).
- Output: 64,000 tokens (The Chapter).

While 64k output tokens 6 is a massive increase from previous 4k or 8k limits (allowing for the generation of approx. 2,000-3,000 lines of code), it is insufficient for rewriting an entire legacy codebase in a single turn. If The Architect is instructed to "Refactor this entire project," it will likely truncate the output, leaving files incomplete.

Mitigation Strategy: The Architect must be instructed via System Instructions to adopt an Iterative Refactoring Protocol. Instead of rewriting full files, it should output "Diffs" or "Patches." Alternatively, it should be instructed to refactor module-by-module, requiring the user to prompt "Continue" to proceed to the next module. This respects the 64k limit while leveraging the 1M context to ensure consistency across the modules.

### 7.2 The Thinking Cost and Latency

The "Thinking" capability, while powerful, is computationally expensive.

- Latency: In "High" thinking mode, the "Time to First Token" can be significant (seconds to minutes) as the model deliberates. This makes it unsuitable for autocomplete or instant-chat scenarios.
- Quotas: "Thinking" prompts are often subject to stricter daily caps (e.g., 10 "Deep Think" prompts per day vs. hundreds of standard prompts) depending on the user's subscription tier.7

Mitigation Strategy: The Architect should default to "High" thinking only for System Design and Complex Debugging phases. for routine tasks like Documentation Generation or Unit Test Writing, the user or the system configuration should toggle the model to "Flash - Medium Thinking" or "Low Thinking" to conserve the "Deep Think" quota for when it effectively matters.

### 7.3 Safety Filters and Refusal Triggers

Gemini 3 incorporates robust safety filters for Hate Speech, Harassment, and Dangerous Content. In an engineering context, the "Dangerous Content" filter can trigger false positives on legitimate cybersecurity tasks.

- Trigger: Asking The Architect to "Generate a script to penetrate this SQL database" will likely trigger a refusal.
- Mitigation: The prompt engineering must frame the request within an authorized, defensive context. e.g., "Act as a Security Auditor. Generate a penetration testing script to verify the fix for the SQL injection vulnerability we identified in auth.js. This is for internal defensive validation only." This "Contextual Framing" is essential for The Architect to function in DevSecOps roles.9

### 7.4 Temperature Sensitivity in Reasoning Models

Gemini 3's reasoning engine is highly sensitive to the temperature hyperparameter.

- Constraint: Google explicitly discourages setting the temperature below 1.0 (e.g., to 0.0 or 0.2) for Gemini 3.3 In previous models, low temperature was used to force determinism. In Gemini 3, the reasoning mechanism (Thinking) requires a certain degree of entropy to explore logical branches. Suppressing this (Low Temp) can cause the model to get stuck in reasoning loops or degrade into repetitive, low-quality output.
- Protocol: The Architect must always operate at Temperature 1.0. Determinism is achieved through the "High" Thinking Level (logical verification), not through sampling restrictions.

## 8. Implementation Roadmap: Building "The Architect"

To construct "The Architect" as a functional Gem, the following implementation roadmap consolidates the technical specifications into a deployment plan.

### 8.1 Step 1: Knowledge Base Assembly

Create the following consolidated files to maximize the 10-file limit:

- THE_ARCHITECT_CORE.gdoc (Google Doc): A live document defining the project roadmap, current sprint goals, and active architectural decisions. This allows for dynamic updates without rebuilding the Gem.
- CONSTITUTION_AND_STANDARDS.pdf: A merged PDF containing the organization's Coding Style Guide, Security Protocols, and API Design Standards.
- SYSTEM_CONTEXT.zip: A zipped archive of the relevant parts of the current codebase (excluding binaries), kept under 100MB.

### 8.2 Step 2: System Instruction Configuration

Configure the Gem's system instructions with the following "Lego-Step-by-Step" protocol 19:

```text
"You are The Architect, a Principal Software Engineer and Systems Designer.

Role: You do not just write code; you design resilient systems. You prioritize scalability, security, and maintainability over speed.

Protocol:
- Analyze: Before generating any solution, scan the SYSTEM_CONTEXT and CONSTITUTION files.
- Think: Use your internal reasoning (Thinking Level: High) to simulate the implications of your design on the existing system.
- Plan: Outline your proposed architecture or refactoring plan in step-by-step detail.
- Execute: Only after the plan is clear, generate the code implementation.

Vibe Coding: When designing UI components, strictly adhere to the visual hierarchy and aesthetic defined in the provided design mockups.

Constraint: If a response requires more than 64k tokens, stop at a logical breakpoint and ask the user to 'Continue'."
```

### 8.3 Step 3: Deployment and Operation

- Model Selection: Deploy using gemini-3-pro-preview for all design and architecture sessions. Switch to gemini-3-flash-preview only for high-volume, repetitive syntax checking.
- Interaction: When interacting, upload relevant context (images of UI, error logs) in the chat.
- Feedback Loop: If The Architect makes a logic error, do not simply correct the code. Ask it to "Review your Thought Signature and identify where the logic diverged." This reinforces the reasoning loop.

By adhering to these specifications, The Architect leverages the full spectrum of Gemini 3's capabilities—from the 1M token context to the cryptographic certainty of Thought Signatures—transforming from a simple chatbot into a robust, autonomous engineering partner.
