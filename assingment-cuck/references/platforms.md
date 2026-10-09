# Host adaptation

Use only the section that matches the actual execution host. This guide lists interchangeable capabilities, not mandatory installations. Use available documented tools, and respect host permissions. Do not install large applications, change global configuration, or upload assignments just to conceal a missing capability.

## Desktop hosts

| Capability | Windows | macOS | Linux |
| --- | --- | --- | --- |
| Paths and shells | Discover workspace and executable paths; use the available PowerShell or cmd syntax | Discover workspace and executable paths; use the actual zsh/bash shell | Discover workspace and executable paths; use the actual bash/sh or configured shell |
| Code execution | Matching interpreter/compiler in a real terminal or IDE | Matching interpreter/compiler in Terminal or a supported IDE | Matching interpreter/compiler in the available terminal or IDE |
| Genuine screenshot | Supported native window/screen capture or an IDE's capture/export feature | Supported native window/screen capture after required permission is granted | Supported desktop/window capture, respecting Wayland/X11 and portal permissions |
| Word editing | Available Word/document API or targeted DOCX libraries | Available Word/document API or targeted DOCX libraries | Available document editor/API or targeted DOCX libraries |
| Visual verification | Available Word/document PDF export and page rasterization | Available Word/document PDF export and page rasterization | Available document-suite PDF export and page rasterization |

- Discover applications before selecting one. Examples include VS Code, specialist IDEs, Microsoft Word, and LibreOffice; none is guaranteed to exist. A runtime installed on one host cannot be assumed to exist on another.
- For ARM or x86 hosts, use a compatible runtime and library build. Do not carry hardcoded executables, drive letters, registry assumptions, or shell commands between platforms.
- Prefer targeted DOCX/OOXML insertion when the application API would rebuild the document or lose content. Reader/library compatibility does not prove that an export will preserve formatting: verify the rendered result.
- macOS may require Screen Recording or Accessibility permission. Linux Wayland may require a user-approved capture portal. Windows and remote sessions may restrict window capture. Never bypass these permissions. If the host cannot capture the required surface, mark that requirement incomplete.
- If the desktop is locked or application automation is unavailable, do not invent window state. Use an authorized alternative host or request user-provided real screenshots.

## Cloud, browser and headless agents

- Use file/attachment APIs and the actual accessible execution runtime. Identify whether execution occurs locally, in a container, in a notebook, or in a remote browser workspace.
- A live browser IDE terminal, executed notebook cell, or online compiler result panel may provide authentic execution screenshots when authorized and suitable. Capture the actual executed application surface using the host's browser capture tool.
- The program must execute in the session whose output is captured. Do not use a local HTML page, image renderer, replayed log, or terminal filled with copied output as a replacement. If the user asks for a specific compiler terminal, another output surface does not qualify without their acceptance.
- Shell/API stdout is genuine execution text, but rendering it in HTML, an image, or a simulated terminal does not turn it into a genuine terminal screenshot. Never use this fallback.
- A headless runtime with no real output surface can execute and validate code, but cannot satisfy a requirement for a desktop/IDE screenshot. Preserve its actual logs and prepare the answer document; clearly report the outstanding capture step. Text-only substitution needs the user's acceptance.
- If document libraries are available, produce the requested file. If only plain text output is possible, return organized answers/source code as a partial deliverable and state that Word insertion/export remains incomplete.

## Phones, tablets and chat-only models

- Read accessible attachments or use OCR/vision if provided. On devices without a local toolchain, use an authorized remote/browser runtime if available.
- If the model has no execution tools, prepare solutions and a per-question run/input checklist, but label code unexecuted. Do not claim error-free execution, compiler access, native screenshots, or edited files.
- User-provided screenshots may be inserted when the visible output corresponds to the final code and question. Record that the run/capture was user-provided; do not pretend the agent executed it. Request the actual source/run evidence if the image alone cannot establish the match.
- A device does not need the same editor or compiler brand as another device, unless the assignment or user explicitly requires it. Preserve the required language, semantics, version constraints, and evidence standard.

## Capability fallback order

1. Use the specifically requested accessible application/host.
2. If no specific surface is required, use a suitable installed environment.
3. Use an authorized remote/browser environment when needed and actually available.
4. If execution, capture, document editing, or visual verification is unavailable, complete independent supported steps and clearly identify what remains. Ask only for the missing input/action needed to complete those steps.

Never upgrade a fallback into a claim that all requirements were fulfilled.
