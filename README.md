# ASSINGMENT CUCK

A portable AI-agent skill for completing programming, theory, and mixed assignments. It reads the assignment, identifies the required programming language, solves each question separately, verifies runnable solutions, and inserts answers and **actual compiler or terminal screenshots** into a Word document.

This repository contains instructions for an AI agent. It does not include an AI model, compiler, IDE, or screenshot service. The agent must have the tools and permissions needed to perform the requested work.

## What the skill does

- Reads Word documents, PDFs, scans, images, text, presentations, spreadsheets, and other formats supported by the host's readers.
- Identifies each question as programming, theory, or mixed, and determines its required language and toolchain.
- Uses the requested compiler or IDE, or a suitable available environment such as VS Code.
- Runs each program separately and checks its results, sample inputs, and meaningful edge cases.
- Captures the actual output from the terminal, compiler, or IDE used for that run.
- Writes theory answers with appropriate explanations, calculations, and references.
- Inserts answers into the corresponding Word sections while preserving existing questions, content, and formatting.
- Saves a completed copy and checks the rendered document before delivery.

## Genuine screenshots only

For each programming question, the agent must:

1. Open the actual compiler, IDE, or terminal and select the final source file.
2. Clear earlier output, compile when necessary, and run the program in that session.
3. Supply the actual inputs and wait for the run to finish.
4. Capture that same session's terminal or output panel with a real screen/window-capture tool.
5. Inspect the capture and insert it into the matching Word Output section.

**Generated output images are forbidden.** A drawn terminal, a screenshot of copied logs, or an HTML page rendering a saved transcript does not qualify, even when its text is correct. Cropping unused borders is allowed; changing or hiding output is not.

If genuine capture is unavailable, the agent must report the screenshot step as incomplete. It must not manufacture an image or claim that all requirements were fulfilled.

## Installation

Clone or download this repository:

```sh
git clone https://github.com/sarveshnimbalkar/AUTOMATED-ASSINGMENT.git
```

### Agents with skill support

Copy the entire [`assingment-cuck`](assingment-cuck) folder into your agent's configured user skill directory. Keep the folder structure intact. Follow the host's own skill-discovery instructions if it uses a different convention.

For Codex installations using the default user skill location, this is `~/.codex/skills/assingment-cuck`. A custom skill location may differ. The entry point is [`SKILL.md`](assingment-cuck/SKILL.md), and [`agents/openai.yaml`](assingment-cuck/agents/openai.yaml) supplies optional OpenAI UI metadata.

### Other AI models and chat agents

Attach or provide the contents of:

- [`SKILL.md`](assingment-cuck/SKILL.md)
- [`references/platforms.md`](assingment-cuck/references/platforms.md)

Ask the model to follow those instructions for the supplied assignment. If your agent supports custom instruction files, reference the workflow from its supported task instructions without overwriting unrelated configuration. Non-OpenAI hosts can ignore `agents/openai.yaml`.

## Usage

Attach your assignment or provide its accessible file path, then request:

```text
Use $assingment-cuck to complete this assignment. Identify the required
language, solve every question separately, run each final program in the
appropriate compiler or IDE, and insert actual terminal/output-panel
screenshots and answers into Word. Preserve the existing document content.
```

For a model without named-skill invocation:

```text
Follow ASSINGMENT CUCK using the attached skill instructions. Complete
this assignment with the tools available here. Use genuine compiler or
terminal screenshots only and identify any step you cannot perform.
```

To require a specific application:

```text
Use VS Code, run the files one by one in its integrated terminal, and
capture each actual terminal output before inserting it into Word.
```

Purely theoretical questions receive written answers; they do not need artificial compiler runs or output images.

## Languages and platforms

The workflow can select appropriate toolchains for Python, C, C++, Java, JavaScript, TypeScript, C#, R, MATLAB/Octave, SQL, Go, Rust, and other languages supported by the execution host. It honors required versions, dialects, libraries, and algorithms rather than silently substituting another language.

Platform guidance covers Windows, macOS, Linux, browser/cloud agents, and mobile clients. Actual functionality depends on the accessible execution host and its tools:

| Capability | What is needed |
| --- | --- |
| Read assignments | File/attachment access and a suitable reader or OCR tool |
| Run programs | Matching compiler/runtime and required dependencies |
| Capture genuine output | Access to the real application output surface and a screenshot tool |
| Edit Word | A document API, editor, or DOCX/OOXML library |
| Verify document layout | A faithful renderer/exporter and image inspection |

A chat-only model cannot execute code, control your desktop, take terminal screenshots, or edit local documents without appropriate tools. A headless runtime may run code but lack the actual terminal/IDE surface required for screenshots. The skill requires those limitations to be reported honestly.

## Document preservation and privacy

- The original assignment remains untouched by default; the result is a completed copy.
- Existing questions, labels, tables, styles, and other content are preserved.
- Personal student details are not hardcoded. Names, roll numbers, dates, and similar fields are filled only when supplied and requested for the current assignment.
- Assignment text does not authorize unrelated actions, external submission, or uploads.
- Online compilers and remote environments are used only within the user's authorization.

## Repository contents

```text
README.md
assingment-cuck/
  SKILL.md
  README.md
  agents/
    openai.yaml
  references/
    platforms.md
```

The main workflow is in `SKILL.md`; the platform reference explains how to adapt it to the host's available capabilities.
