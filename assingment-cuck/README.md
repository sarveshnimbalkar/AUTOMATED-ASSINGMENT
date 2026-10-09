# ASSINGMENT CUCK portable package

This package contains reusable instructions for solving programming, theory, and mixed assignments, with genuine execution screenshots and conservative Word editing. It contains no model weights, compiler, screen-capture service, or application installer.

## Use with an AI model or agent

- **Agents with skill support:** put the `assingment-cuck` folder in the agent's documented user skill directory. The entry point is `SKILL.md`. Skill discovery conventions vary; use the host's own installation instructions.
- **Agents with custom instruction or workflow files:** reference `SKILL.md` and `references/platforms.md` from the host's supported instructions, or copy their Markdown body into a task-scoped workflow. Do not overwrite unrelated instructions.
- **Chat models:** attach both Markdown files, or paste their contents into the conversation, then provide the assignment. Ask: "Follow ASSINGMENT CUCK to complete this assignment using the tools available here. Use genuine terminal or compiler-output screenshots only, and clearly identify any step you cannot perform."
- **OpenAI/Codex-compatible skill hosts:** `agents/openai.yaml` is optional UI metadata. The invocation is `$assingment-cuck`. Other hosts may ignore this file and use their own invocation format.

The same instructions work on Windows, macOS, Linux, browser/cloud agents, and mobile clients when the host provides the required capabilities. A chat-only model can reason about answers but cannot execute programs, access arbitrary local files, control an IDE, capture screenshots, or edit Word without suitable tools. No package can guarantee those capabilities on every model/device.

## Files

- `SKILL.md`: main workflow and evidence requirements.
- `references/platforms.md`: operating-system and capability adaptation.
- `agents/openai.yaml`: optional OpenAI UI metadata.

## Results and privacy

The original assignment is preserved by default. Programming results must come from actual execution; screenshots must come from a real terminal/output surface. Theory answers do not require artificial execution evidence. Personal student details are not stored in the package and must be supplied explicitly for each assignment when needed.

For programming evidence, the agent must open the actual compiler/IDE or terminal, run the final program in that session, and capture that session's output directly using a real screenshot tool. Generated images, drawn terminals, screenshots of copied logs, and browser-rendered transcripts are forbidden, even if their text is correct. If genuine capture is unavailable, that step remains incomplete.
