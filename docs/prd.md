# PRD: Cline based AI agents system prompt fine tuning

## 1. Product overview

### 1.1 Document title and version

- PRD: Cline based AI agents system prompt fine tuning
- Version: 0.0.1

### 1.2 Product summary

This document outlines the product requirements for a Visual Studio Code extension, identified as `kvokka.cline_system_prompt`. The extension, titled "Cline based AI agents system prompt fine tuning," aims to provide developers with tools to customize, manage, and fine-tune the system prompts used by AI-driven coding assistants within their IDE.

The initial phase of this project will focus on establishing a foundational boilerplate: a functional VS Code extension that activates and can execute a simple "Hello World" command. This groundwork is crucial for subsequent development. Future phases will build upon this base to incorporate functionalities for interacting with system prompts, initially targeting the 'Cline' (`saoudrizwan.claude-dev`) extension. The long-term vision includes exploring and potentially integrating compatibility with other AI assistant extensions like 'roo-code' and 'kilo', allowing users a centralized way to manage and optimize AI agent behavior through prompt engineering.

## 2. Goals

### 2.1 Business goals

- Establish a new VS Code extension under the `kvokka` publisher, creating a presence in the AI developer tools space.
- Lay the foundation for a product that can attract developers interested in customizing AI coding assistant behavior.
- Create a modular extension that can be expanded to support multiple AI assistant tools in the future.

### 2.2 User goals

- (Phase 1) Successfully install and activate a basic, functional VS Code extension.
- (Phase 1) Verify the extension is working by triggering a simple command (e.g., "Say Hello").
- (Future) Gain more control over the system prompts used by AI coding assistants like Cline.
- (Future) Improve the performance and relevance of AI-generated code/suggestions by fine-tuning system prompts.
- (Future) Experiment with different system prompt configurations easily within the VS Code environment.
- (Future) Potentially manage system prompts for multiple AI extensions (Cline, roo-code, kilo) from a single interface.

### 2.3 Non-goals

- (Phase 1) Implementing the full system prompt fetching, editing, and application logic.
- (Phase 1) Building any UI beyond a simple information message for the "Hello World" command.
- (Phase 1) Achieving full compatibility with roo-code or kilo extensions.
- Replicating the full functionality of the Cline extension itself.
- Providing a general-purpose AI chat interface.

## 3. User personas

### 3.1 Key user types

- Software Developers using VS Code.
- AI Enthusiasts and Prompt Engineers.
- Users of the Cline (`saoudrizwan.claude-dev`) VS Code extension.
- Potential users of roo-code and kilo VS Code extensions.

### 3.2 Basic persona details

- **Alex (Developer & Cline User)**: An experienced software developer who uses VS Code daily and relies on the Cline extension for AI-assisted coding. Alex wants to optimize Cline's behavior for specific project contexts by tweaking its system prompt.
- **Sam (Prompt Engineer)**: A developer with a keen interest in prompt engineering. Sam is looking for tools that allow experimentation and fine-tuning of system prompts for various AI models and tasks directly within the IDE.
- **Jamie (Multi-Extension User)**: A developer who might use Cline, and is also exploring or using other AI extensions like roo-code or kilo. Jamie would appreciate a unified way to manage prompts if possible.

### 3.3 Role-based access

- **Extension User**: (Single role for this type of tool)
- Can install and uninstall the extension.
- Can execute commands provided by the extension.
- (Future) Can access settings to configure the extension.
- (Future) Can view, edit, and apply system prompt configurations.

## 4. Functional requirements

- **FR-001: Extension Activation** (Priority: High - Phase 1)
- The extension must activate successfully when VS Code starts or when its activation events are triggered.
- For Phase 1, activation can be tied to a specific command.
- **FR-002: "Say Hello" Command** (Priority: High - Phase 1)
- The extension must contribute a command (e.g., `kvokka.cline_system_prompt.sayHello`).
- When triggered, this command must display a simple, non-intrusive "Hello World" message (e.g., using `vscode.window.showInformationMessage`).
- **FR-003: Declare Cline Dependency** (Priority: Medium - Phase 1)
- The extension's `package.json` should declare `saoudrizwan.claude-dev` as an `extensionDependency` to signify its intended relationship, even if direct interaction is not part of Phase 1.
- **FR-004: View Base System Prompt (Future)** (Priority: High - Phase 2)
- The extension should allow users to view the current or a base system prompt (e.g., derived from Cline's logic).
- **FR-005: Modify System Prompt (Future)** (Priority: High - Phase 2)
- The extension should provide a mechanism for users to edit or "rework" the system prompt.
- **FR-006: Apply/Use Reworked Prompt (Future)** (Priority: High - Phase 2)
- The extension should enable the user to apply their fine-tuned prompt in a way that influences the targeted AI agent's behavior (details TBD).
- **FR-007: roo-code Compatibility (Future)** (Priority: Medium - Phase 3)
- Investigate and implement mechanisms to interact with or manage system prompts for the 'roo-code' extension.
- **FR-008: kilo Compatibility (Future)** (Priority: Medium - Phase 3)
- Investigate and implement mechanisms to interact with or manage system prompts for the 'kilo' extension.

## 5. User experience

### 5.1. Entry points & first-time user flow

- **Installation**: User installs the "Cline based AI agents system prompt fine tuning" extension from the VS Code Marketplace.
- **Activation**: The extension activates (e.g., upon command invocation).
- **First Use (Phase 1)**:
- User opens the command palette (Ctrl+Shift+P or Cmd+Shift+P).
- User searches for and selects the "CSP Tuner: Say Hello" command.
- A "Hello World" information message appears.

### 5.2. Core experience

- **Phase 1 - "Hello World"**:
- **Trigger Command**: User executes the "CSP Tuner: Say Hello" command via the command palette.
- The experience should be immediate and confirm the extension is installed and working. A simple information message is sufficient.
- **Future - Prompt Tuning Workflow (Conceptual)**:
- **Access Prompt**: User invokes a command to view/edit the current system prompt for a target AI (e.g., Cline).
  - The prompt is displayed in an editable VS Code document or webview.
- **Modify Prompt**: User makes changes to the system prompt text.
  - Standard text editing features should be available.
- **Apply Prompt**: User triggers an action to save and apply the modified prompt.
  - The extension updates its configuration or interacts with the target AI extension (if an API exists or can be developed) to use the new prompt.
- **Observe Results**: User interacts with the target AI agent to see the effect of the prompt changes.

### 5.3. Advanced features & edge cases

- (Phase 1) No advanced features or significant edge cases beyond ensuring the command appears and executes.
- (Future) Managing multiple prompt profiles.
- (Future) Reverting to default prompts.
- (Future) Handling cases where target extensions (Cline, roo-code, kilo) are not installed or are different versions.
- (Future) Error handling if prompt application fails.

### 5.4. UI/UX highlights

- (Phase 1) Minimalist: Only a command palette entry and an information message.
- (Future) Intuitive interface for viewing and editing prompts (e.g., a dedicated editor tab or webview).
- (Future) Clear feedback to the user when prompts are loaded, saved, or applied.
- (Future) Non-intrusive notifications.

## 6. Narrative

Alex, a software developer, uses the Cline AI extension in VS Code but feels its responses could be more tailored to their specific coding style and project requirements. Alex wants to fine-tune the underlying system prompt that guides Cline but finds no easy way to do this directly. Discovering the "Cline based AI agents system prompt fine tuning" extension (`kvokka.cline_system_prompt`), Alex installs it. (In future versions) Alex uses the new extension to view Cline's base system prompt, makes modifications to emphasize certain coding practices, and applies the new prompt. As a result, Alex finds Cline's suggestions more aligned with their needs, improving productivity and code quality.

## 7. Success metrics

### 7.1. User-centric metrics

- (Phase 1) Number of successful "Say Hello" command executions.
- (Future) Number of active users.
- (Future) Frequency of prompt modifications.
- (Future) User retention rate.
- (Future) Qualitative feedback (e.g., marketplace reviews, GitHub issues/discussions) indicating improved AI agent performance due to prompt tuning.

### 7.2. Business metrics

- Number of installs from the VS Code Marketplace.
- (Future) Growth rate of active users.
- (Future) Mentions or adoption by the Cline/roo-code/kilo user communities.

### 7.3. Technical metrics

- (Phase 1) Extension load time.
- (Phase 1) Absence of errors on activation or command execution.
- (Future) Performance of prompt loading/saving operations.
- (Future) Stability and low error rates.
- (Future) Compatibility with specified versions of VS Code and target AI extensions.

## 8. Technical considerations

### 8.1. Integration points

- VS Code API (commands, information messages, configuration, potentially webviews or custom editors in the future).
- (Future) Interaction with the `saoudrizwan.claude-dev` (Cline) extension. This might involve:
- Reading its configuration if possible.
- Attempting to invoke its APIs if any are exposed for prompt management (currently unlikely for direct system prompt access).
- Replicating/adapting its prompt generation logic if direct access remains infeasible.
- (Future) Similar investigation and integration points for `roo-code` and `kilo` extensions.

### 8.2. Data storage & privacy

- (Phase 1) No user data is stored.
- (Future) User-modified prompts will need to be stored, likely in VS Code's extension settings (workspace or global scope) or dedicated files within the workspace.
- No sensitive personal data will be collected or stored. Prompts are user-generated content related to coding.

### 8.3. Scalability & performance

- (Phase 1) Negligible impact.
- (Future) Prompt management should be efficient. Loading and saving prompts should be near-instantaneous.
- The extension should not degrade VS Code performance.

### 8.4. Potential challenges

- (Future) Accessing or influencing system prompts of other extensions (Cline, roo-code, kilo) if they don't provide explicit APIs. This might require reverse engineering (discouraged for stable solutions) or maintaining parallel logic.
- (Future) Keeping up with changes in the target extensions if prompt logic is copied/adapted.
- (Future) Defining a clear and intuitive UX for prompt editing and management.
- (Future) Ensuring compatibility across different versions of target extensions.

## 9. Milestones & sequencing

### 9.1. Project estimate

- Small (for Phase 1: "Hello World" boilerplate and PRD)

### 9.2. Team size & composition

- Small Team: 1 developer (for initial boilerplate)
- (Future, for full features) May require 1-2 engineers.

### 9.3. Suggested phases

- **Phase 1**: Basic Boilerplate & Documentation (Target: ~1-2 days)
- Key deliverables:
- Functional VS Code extension (`kvokka.cline_system_prompt`) with a "Say Hello" command.
- `package.json` configured with name, display name, publisher, basic command.
- This PRD document (`docs/prd.md`).
- Initial update to the main `README.md` about the extension's intent.
- **Phase 2**: Cline Prompt Viewing & Basic Reworking (Target: TBD, post-Phase 1)
- Key deliverables:
- Ability to fetch/replicate and display Cline's system prompt.
- Basic UI/editor for users to modify the prompt.
- Mechanism to store and use the reworked prompt (initially, could be for local use/display before influencing Cline directly).
- **Phase 3**: Advanced Prompt Management & Initial Multi-Extension Exploration (Target: TBD)
- Key deliverables:
- Robust prompt management features (profiles, versioning if needed).
- Investigation and PoC for roo-code/kilo compatibility.

## 10. User stories

### 10.1. Install and verify basic extension functionality (Phase 1)

- **ID**: US-001
- **Description**: As a VS Code user, I want to install the "Cline based AI agents system prompt fine tuning" extension and run a simple command so that I can verify it is installed correctly and active.
- **Acceptance criteria**:
- The extension can be found and installed from the VS Code Marketplace (or via VSIX for local testing).
- After installation, a command like "CSP Tuner: Say Hello" is available in the command palette.
- Executing the "CSP Tuner: Say Hello" command displays an information message (e.g., "Hello World from Cline System Prompt Tuner!").
- The extension activates without errors.

### 10.2. View current system prompt for Cline (Future - Phase 2)

- **ID**: US-002
- **Description**: As a developer using Cline, I want to view the effective system prompt being used by Cline so that I understand its current guiding instructions.
- **Acceptance criteria**:
  - A command exists to trigger the display of the Cline system prompt.
  - The displayed prompt accurately reflects the base system prompt (either fetched or generated based on Cline's logic).
  - The prompt is displayed in a readable format (e.g., a VS Code text editor or a dedicated read-only view).

### 10.3. Modify and save a custom system prompt for Cline (Future - Phase 2)

- **ID**: US-003
- **Description**: As a developer using Cline, I want to modify the system prompt and save my custom version so that I can fine-tune Cline's behavior for my specific needs.
- **Acceptance criteria**:
  - The user can edit the displayed system prompt.
  - The user can save the modified prompt.
  - The saved prompt is persisted (e.g., in extension settings or a workspace file).
  - (Further ACs on how this modified prompt *influences* Cline would depend on the technical implementation chosen for applying the prompt).
