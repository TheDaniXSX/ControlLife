# Cursor Code Editor Cheat Sheet

## AI Modes

### Ask (Chat)
- Q&A without direct code edits.
- Ideal for explanations, debugging, and planning.

### Edit Mode
- Single-turn code edits with immediate changes.
- Quick refactoring or bug fixing.

### Agent Mode
- Multi-step reasoning and actions (code search, file management, terminal, web search).
- Ideal for complex tasks or cross-file modifications.

## Creating Custom Agent Tools (MCP)
1. **Implement MCP Tool** (in any language, communicates via stdout/HTTP).
2. **Run MCP Server** locally/remotely.
3. **Register Tool** (Cursor Settings → MCP).
4. **Verify and Prompt** agent to use explicitly if needed.

## Cursor Rules

### Project Rules
- Stored in `.cursor/rules/*.mdc`.
- Applied automatically to specified file patterns.
- Include guidelines, style preferences, and file references (`@file`).

### Global Rules
- Apply universally across projects.
- Configured in Cursor Settings → Rules for AI.

## Prompt Engineering Tips
- Include context with `@file`.
- Use specific, detailed instructions.
- Guide Agent with numbered steps.
- Few-shot examples improve accuracy.
- Cycle models (`Cmd+/`) for varied responses.

## Workflow Integration
- Integrated IDE features (terminal, source control, navigation).
- AI-generated commit messages.
- AI-driven testing/debugging cycles (YOLO mode).
- Collaborative sharing of project rules.

## Customizing Behavior
- Select AI models or use personal API keys.
- Toggle Autocontext and use `.cursorignore`.
- Configure command guardrails and YOLO mode.
- Customize themes, keybindings, and extensions.

## File Management & Navigation
- Quick Open (`Cmd+P`) and global search (`Cmd+Shift+F`).
- Semantic file/code searches via AI queries.
- File creation/deletion via Agent commands.

## Debugging with AI
- Explain errors with context.
- Step-by-step debugging via Agent (terminal commands, YOLO mode).
- Semantic codebase search to locate issues.

## Keyboard Shortcuts
- **Agent Panel:** `Cmd+I`
- **Ask Panel:** `Cmd+L`
- **Inline AI:** `Cmd+K`
- **Cycle Mode:** `Cmd+.`
- **Cycle Model:** `Cmd+/`
- **Submit/Accept:** `Cmd+Enter`
- **Cancel/Reject:** `Cmd+Backspace`
- **New Chat:** `Cmd+N`
- **History Panel:** `Cmd+Alt+L`
- **Autocomplete:** `Tab`
- **Command Palette:** `Cmd+Shift+P`

## Productivity Boosters
- Multi-line AI code suggestions.
- Quick apply from chat.
- AI-powered commit messages.
- Experimental Notepads for reusable context.

---

## Twitter tricks
Cursor trick: after it generates a plan, before having it implement the plan, say:

"Can we do this with less code? Look for opportunities to make this code more elegant and give me a report with your best ideas."

---

## References
- [Cursor Documentation](https://cursor.sh/docs)
- [Model Context Protocol (MCP)](https://cursor.sh/docs/mcp)
- [Creating and Managing Rules](https://cursor.sh/docs/rules)
- [Keyboard Shortcuts Reference](https://cursor.sh/docs/shortcuts)

- [Awesome CursorRules](https://github.com/PatrickJS/awesome-cursorrules)