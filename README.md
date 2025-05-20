# Cline System Prompt Tuner (kvokka.cline_system_prompt)

This repository contains the source code for the **Cline System Prompt Tuner** VS Code extension, published under the ID `kvokka.cline_system_prompt`.

## Purpose

The "Cline System Prompt Tuner" is a Visual Studio Code extension designed to provide developers with tools to customize, manage, and fine-tune the system prompts used by AI-driven coding assistants, with an initial focus on the 'Cline' (`saoudrizwan.claude-dev`) extension.

The long-term vision includes:

- Allowing users to view and modify the base system prompts.
- Enabling experimentation with different prompt configurations to optimize AI agent behavior.
- Exploring compatibility with other AI assistant extensions like 'roo-code' and 'kilo'.

## Current Status (Phase 1)

The project is currently in its initial phase, focusing on:

- Establishing the basic VS Code extension boilerplate.
- Implementing a simple "Hello World" command to verify installation and activation.
- Creating foundational documentation, including a Product Requirements Document (PRD).

For detailed product requirements and future plans, please see the [PRD located in docs/prd.md](docs/prd.md).

## Getting Started (Development)

1. Clone the repository.
2. Install dependencies: `npm install`
3. Compile the extension: `npm run compile` (or `npm run watch` for development)
4. Lint the code: `npm run lint` (ensure no errors before proceeding)
5. Open the project in VS Code and press `F5` to launch the Extension Development Host.

_*Templated from [kvokka/getting-started](https://github.com/kvokka/getting-started)*_
