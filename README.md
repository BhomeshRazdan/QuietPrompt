https://github.com/BhomeshRazdan/QuietPrompt/releases

# QuietPrompt: Local-First Copilot-Style AI Assistant, Fully Offline

[![Releases](https://img.shields.io/badge/QuietPrompt-Release-Assets-brightgreen?style=for-the-badge&logo=github&logoColor=white)](https://github.com/BhomeshRazdan/QuietPrompt/releases)

🧠 Local-first, Copilot-style AI assistant that runs offline. QuietPrompt uses screen, mic, and clipboard input to fetch results from an on-device or locally hosted AI model. No cloud, no vendor lock-in, and no data sent off your machine. Press a key, get results. Simple, fast, private.

---

## Table of contents

- [Overview](#overview)
- [Why QuietPrompt?](#why-quietprompt)
- [Key features](#key-features)
- [How it works](#how-it-works)
- [Supported inputs and outputs](#supported-inputs-and-outputs)
- [Getting started](#getting-started)
- [Installation and downloads](#installation-and-downloads)
- [Configuration and workflows](#configuration-and-workflows)
- [Privacy, security, and offline design](#privacy-security-and-offline-design)
- [Extensibility and plugins](#extensibility-and-plugins)
- [Developer guide](#developer-guide)
- [Usage examples](#usage-examples)
- [Troubleshooting](#troubleshooting)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [Changelog](#changelog)
- [License](#license)

---

## Overview

QuietPrompt is a local-first assistant designed to feel like a modern Copilot. It connects to any local LLM or OCR engine you point it to, and it operates entirely offline. It uses three powerful input channels—screen capture, microphone input, and clipboard data—to construct prompts, run queries, and deliver results in real time. You can customize the setup to match your preferred stack: your favorite LLM, your preferred OCR engine, and your chosen UI skin. The goal is a smooth, private workflow that respects your data and your device’s performance.

Images update the mental model of the product. See the brain image for the concept of on-device thinking, the lock image for privacy, and the laptop image for desktop usage.

- Brain icon: ![Brain](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Brain_icon.png/120px-Brain_icon.png)
- Lock icon: ![Lock](https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/Lock_icon.png/120px-Lock_icon.png)
- Laptop icon: ![Laptop](https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Laptop_icon.png/120px-Laptop_icon.png)

---

## Why QuietPrompt?

- Privacy by design: all processing happens on your device unless you opt into a trusted local service. No data leaves your machine by default.
- True offline capability: run with a fully offline stack or with a local adapter that talks to a private model.
- Flexible input models: capture data from the screen, your voice, or your clipboard. Mix and match as needed.
- Open, adaptable: designed to work with any LLM or OCR engine. Swap engines without changing workflows.
- No vendor lock-in: keep control of your tools, data, and prompts. Promote reproducible results and faster iteration.

QuietPrompt is built for developers, researchers, data scientists, and knowledge workers who want predictable privacy and consistent performance.

---

## Key features

- Local-first operation: all core tasks run locally with optional remote decoupling.
- Multi-input prompts: combine screen data, voice queries, and clipboard content into a single prompt.
- Pluggable engines: swap LLMs and OCR engines with minimal changes to the pipeline.
- Keyboard-first workflow: hotkeys launch prompts and display results instantly.
- Output controls: copy results to clipboard, export to files, or stream to other tools.
- Fine-grained privacy controls: enable or disable data logging, optionally redact sensitive content.
- Lightweight UI: responsive interface that stays out of your way when you need speed.
- Cross-platform: designed to work on Windows, macOS, and Linux with consistent behavior.

---

## How it works

QuietPrompt acts as an orchestration layer. It listens for input from three channels—screen, mic, and clipboard. It then builds a prompt template, sends the prompt to a local model or local OCR pipeline, receives the answer, and renders it in the UI. The pipeline is modular:

- Input layer: screen capture module, microphone capture module, clipboard watcher.
- Prompt builder: formats user intent into a query your LLM can understand.
- Model adapters: adapters for local LLMs, including CPU/GPU-accelerated variants, and OCR engines.
- Output renderer: shows results, highlights, and contextual info in the UI.
- Storage: caches recent prompts, responses, and model metadata locally.
- Plugins: optional extensions that add features like code execution, document parsing, or data extraction.

This architecture keeps your data on your device and lets you mix and match engines for different tasks.

---

## Supported inputs and outputs

- Screen input: capture UI state, text, and layout from any screen region. Use OCR to extract text as needed.
- Microphone input: record questions or commands. Transcripts can be fed directly to the prompt engine.
- Clipboard input: paste text, images, or other data to seed the prompt.
- Outputs: on-screen results, clipboard copy, file exports (text, JSON, or custom formats), and optional post-processing with local tools.

The design favors fast feedback. Results appear as soon as the model returns a response. You can then refine your prompt and re-run without leaving the context.

---

## Getting started

- Prerequisites: a local environment you control, compatible hardware, and access to at least one local LLM or OCR engine. QuietPrompt is designed to be agnostic to the exact engine.
- Hardware: a modern CPU, at least 8 GB RAM for light tasks, more for heavy workloads. A GPU helps for large models, but it is not required for core offline features.
- Operating systems: the project aims to run on Windows, macOS, and Linux. Build steps are provided in the installation guide.

To begin, download the latest release from the Releases page, extract it, and run the launcher for your platform. Your chosen LLM and OCR engines can be wired up after the initial setup. The most important idea is this: you press a key, you get results. The rest is configuration.

Note: The Releases page is the central place for binaries and assets. For quick access, visit the Releases section to grab the installer or portable package that matches your system.

---

## Installation and downloads

- Download the latest release from the official page: https://github.com/BhomeshRazdan/QuietPrompt/releases
- Choose the package that fits your system:
  - Windows: QuietPromptSetup.exe or QuietPrompt-portable.zip
  - macOS: QuietPrompt.dmg or QuietPrompt.app
  - Linux: QuietPrompt.AppImage or a distribution-specific package
- After download, run the installer or extract the portable package.
- On first launch, QuietPrompt will prompt you to select:
  - Local LLM engine: choose from your installed models or adapters.
  - OCR engine: select an OCR option that suits your document types.
  - Keyboard shortcuts: customize hotkeys for quick access.
- Configure privacy settings:
  - Enable local logging for debugging only.
  - Disable data sharing by default.
  - Opt into optional telemetry if you want to help improve offline tooling.
- Optional: connect to a private local service for model updates or prompt improvements. This keeps everything on your network or machine.

If the link above fails, you can also check the Releases section for the latest assets and instructions.

The link is useful for direct downloads, assets, and release notes. Visit https://github.com/BhomeshRazdan/QuietPrompt/releases to browse the latest items.

---

## Configuration and workflows

- Initial setup
  - Install the chosen LLM and OCR engines locally.
  - Start QuietPrompt and confirm the UI loads correctly.
  - Pick a default prompt template for common tasks (summaries, code generation, research notes, data extraction).
- Daily workflow
  - Use a global hotkey to bring up QuietPrompt.
  - Capture a screen region for context or paste text from the clipboard.
  - Speak a command or question if you prefer voice input.
  - Review the result in the UI; adjust the prompt if needed and re-run.
- Task-specific templates
  - Code assistance: extract code chunks from screenshots and generate explanations.
  - Data extraction: pull fields from forms or scanned documents.
  - Meeting notes: synthesize highlights from disjoint sources.
- Privacy options
  - Turn on differential privacy to obscure sensitive content before processing.
  - Keep a local cache of prompts for quick recall without sending data to any external server.
- About adapters
  - LLM adapters: swap in a different model or host, as long as it speaks the expected API.
  - OCR adapters: switch between OCR engines for better recognition on certain document types.
- Debugging
  - Use the built-in logs to inspect prompt formation, model responses, and any translation steps.
  - Clear caches to troubleshoot stale results or misbehavior.

Shortly after setup, you should have a smooth cycle: select input, trigger processing, view result, refine, and reuse.

---

## Extensibility and plugins

QuietPrompt embraces a modular design. Plugins can extend both input modalities and processing capabilities. Examples:

- New input adapters: add support for camera-based capture, handwriting recognition, or web page capture.
- New OCR engines: plug in engines optimized for scanned docs, receipts, or multilingual text.
- New model adapters: connect to a private model store, edge devices, or a containerized local server.
- Post-processing plugins: code beautifiers, data validators, or domain-specific parsers.

Plugin authors should follow the documented interface patterns. Plugins can register themselves with the core at startup, advertise capabilities, and expose configuration options in the UI. This makes it easy to tailor QuietPrompt to a niche workflow while preserving the core experience.

---

## Developer guide

- Project structure (high level)
  - core/ — core orchestration and prompt logic.
  - ui/ — cross-platform user interface components.
  - adapters/ — model and OCR adapters with a common interface.
  - plugins/ — optional extensions.
  - data/ — local storage for prompts, results, and metadata.
  - docs/ — developer and user docs.
- Build and run
  - Ensure you have the required toolchain for your platform.
  - Run the provided build script to compile and package for Windows, macOS, or Linux.
  - Test input capture, prompt creation, and result rendering across platforms.
- Contribution workflow
  - Open an issue to discuss a feature.
  - Create a branch for the feature or fix.
  - Implement tests for any new behavior.
  - Submit a pull request with a concise summary of changes.
  - Run the test suite locally before proposing changes.
- Testing philosophy
  - Unit tests cover prompt building and adapter interfaces.
  - Integration tests verify end-to-end flows with mock engines.
  - Manual testing validates UI responsiveness and hotkeys.
- Localization
  - The UI supports multiple languages. Add translations under the locales directory.
  - Ensure prompts and examples are friendly to non-English contexts.
- Accessibility
  - Keyboard navigation is supported.
  - Screen reader labels exist for all major controls.
  - High-contrast themes are available.

If you’re contributing, you help improve privacy, performance, and ease of use. Your work helps others adopt a private, offline AI workflow.

---

## Usage examples

- Example 1: Quick screen-based data extraction
  - Step 1: Press the global hotkey to open QuietPrompt.
  - Step 2: Choose a screen region that contains the form you want to extract.
  - Step 3: Run OCR to convert the region to text.
  - Step 4: Prompt the model to extract fields and format the data as JSON.
  - Step 5: Copy the JSON to the clipboard or export to a file.

- Example 2: Voice-assisted research note
  - Step 1: Start a voice query: “Summarize the key points from the highlighted section.”
  - Step 2: QuietPrompt uses your OCR and LLM adapters to fetch a concise summary.
  - Step 3: Paste the summary into your notes, with citations if needed.

- Example 3: Local code assistance
  - Step 1: Capture a code snippet from a screen region or clipboard.
  - Step 2: Prompt the model to explain the algorithm and suggest improvements.
  - Step 3: Export a mention of the insights to your code editor or a document.

- Example 4: Multimodal task orchestration
  - Step 1: Provide a mixed input: a screenshot, a voice question, and a pasted table.
  - Step 2: QuietPrompt combines inputs, runs a multi-step prompt, and returns a unified result.
  - Step 3: Save the outcome as structured data for later use.

- Example 5: Privacy-focused data extraction
  - Step 1: Enable on-device redaction.
  - Step 2: Run OCR on sensitive documents.
  - Step 3: Generate a sanitized report that omits or masks sensitive fields.

These examples illustrate flexible workflows. Each user can tailor QuietPrompt to their own tasks.

---

## Privacy, security, and offline design

- Data locality: most data stays on your device. You control where prompts and results are stored.
- Local processing: core tasks run on-device when possible. Offline operation is supported and encouraged for sensitive tasks.
- Optional remote updates: you can opt into remote updates or keep everything offline. Your choice governs how you receive model improvements.
- Minimal telemetry: if enabled, telemetry collects only essential usage data to help improve the product.
- Export controls: you can export results without exposing intermediate prompts or raw inputs if you enable redaction settings.
- Clear data lifecycle: you can delete prompts and results from the local store at any time.
- Security posture: the system respects OS permissions for capture, storage, and process isolation. You decide which engines and adapters to trust.

QuietPrompt is designed for people who value privacy and control. It gives you the tools to build efficient, private AI-assisted workflows without relying on the cloud.

---

## Accessibility and user experience

- Clear UI: a simple, consistent interface makes it easy to use without a manual.
- Keyboard-first design: primary actions are accessible via the keyboard.
- Visual feedback: progress indicators help you understand where a task stands.
- Clear prompts: templates and prompts are documented to guide you in building effective queries.
- No fluff: settings and options are described plainly so you can tune the tool without guesswork.

The experience emphasizes calm confidence. It should feel reliable and straightforward, not flashy or hype-driven.

---

## Roadmap

- Enhanced multimodal pipelines: tighter integration of screen, voice, and text inputs.
- More local engine options: additional local LLMs and OCR engines with optimized adapters.
- Advanced privacy modes: granular controls for redaction, logging, and data routing.
- Improved offline performance: smarter caching and model loading strategies to reduce startup time.
- Better experimentation support: built-in A/B testing for prompt templates and adapters.
- Community-driven plugins: a robust ecosystem for input methods, post-processing, and analytics.

The roadmap aims for steady, practical improvements that keep the tool useful in real work.

---

## Contributing

- Read the contributing guide in the repo to understand the workflow.
- Start with issues labeled “good first issue” to learn the codebase.
- Propose features with a short rationale and a sketch of the implementation.
- Share tests that demonstrate new behavior or bug fixes.
- Respect project standards for code style, documentation, and tests.
- Be respectful in discussions. The project values clarity and collaboration.

Contributions help more people use quiet, private AI workflows that stay on their machines.

---

## Changelog

- v0.x.y — Initial private beta with core offline support and three input modalities.
- v0.x.z — Added pluggable adapters for local LLMs and OCR engines; improved prompt templates.
- v0.x.y+1 — UI improvements, hotkey customization, and export options.
- v1.0.0 — Stable release with cross-platform packaging and privacy controls.
- v1.0.1+ — Minor updates to performance, documentation, and accessibility.

The changelog tracks improvements to private AI workflows, not the cloud. Each release page lists the exact changes and assets.

---

## License

QuietPrompt is released under the MIT License. See the LICENSE file for details.

---

## Download and install again

For direct access to binaries and release notes, visit the official Releases page: https://github.com/BhomeshRazdan/QuietPrompt/releases

If you need to download the latest assets, check the Releases page again to pick the right package for your system. The page contains the executable installers and portable bundles you can run directly on your machine. This ensures you have the most up-to-date, locally hosted components for your environment.

—


