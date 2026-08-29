# Contributing Guide

## How to Add a New Prompt?
1. Copy from `templates/prompt-template.md`
2. Place it in the relevant folder
3. Name the file in kebab-case: `my-awesome-prompt.md`
4. Fill in the YAML frontmatter fields
5. Include System Prompt + Variables + Example Usage sections

## The Folder Rule (prompts with extra files)
A prompt with **only** its `.md` (+ optional `.fa.md`) stays directly in the category folder. If your prompt has **any extra files** — knowledge-base documents, reference files, example images/videos, sample outputs — it must get its own folder:

```
prompts/<category>/my-prompt-name/
├── my-prompt-name.md        # English prompt
├── my-prompt-name.fa.md     # Persian version (optional)
├── kb/                      # ALL knowledge-base / reference files
└── examples/                # example runs, inputs/outputs, media (optional)
```

- The folder is named exactly after the prompt (kebab-case, same as the `.md` filename).
- Prompt files sit at the folder root — never inside `kb/`.
- Knowledge files keep the exact filenames the system prompt references (platforms match knowledge files by name).
- Never leave extra files loose in the category folder.

## Quality Standards
- Test your prompt before submitting
- Write clean, clear prompts (English or Persian)
- No spam or low-effort submissions
- Follow the existing folder structure

## File Naming Convention
- English prompts: `descriptive-name.md`
- Persian prompts: `descriptive-name.fa.md`

## Pull Request Process
1. Fork the repository
2. Create your prompt file
3. Test it with at least one LLM
4. Submit a PR with a clear description

## Questions?
Open an issue if you need help or clarification.
