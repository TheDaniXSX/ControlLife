# Cursor Code Editor Cheat Sheet

## Tips

1. setup proper cursor rules in .cursor/rules with specific domain knowledge
    - cursor-rules.mdc          - general rules for creating new rules, or for steps to take in acount always
    - project-structure.mdc     - guide of how to structure the project
    - expo.mdc                  - general expo rules for what is using and things to take in account
    - todo.mdc                  - guide how to expand and maintain the todo.md
        - Future tasks
        - In-progress tasks
        - Completed tasks
        - ![task-list](C:\Users\VirtualR3\AndroidStudioProjects\ControlLife\docs\dani\tasl-list.jpeg)
    - git.mdc                   - guide of when and how to do a commit, you can create a command so the agent do all the terminal steps to the push with one prompt
    - block.mdc                 - guides of how to instanciate and adapt blocks of code, one .mdc for each block

    - Stored in `.cursor/rules/*.mdc`.
    - Declare where diferent files are located
    - Declare how you want your code and comments
    - Declare how you want your text files to be written
    - Declare how much you want or not to make in each action
    - Define how each .mdc should be accesed or passed to de LLM
    - Global rules
        - Apply universally across projects.
        - Configured in Cursor Settings → Rules for AI.
    - [Cursor Rules](https://cursor.directory/rules)

2. break down tasks into small incremental steps instead of tackling everything at once

3. use git for version control as a safety net
    - decide how often a commit is needed
    - define how to decide commit names

4. create documentation files (prd.md, specs.md) as reference context for the ai
    - define all the .md files to documentate the project
    - todo.md                   - documents the next and past tasks and subtasks, need to be maintained
    - ideas.md                  - fast ideas that are not worked and organized
    - project.md                - defines the project, 

5. use @ references to provide specific context from files

6. start new chats for each task to avoid context bloat

7. use reasoning models (e.g 3.7 max mode) for planning, regular models for implementation

8. add detailed comments about your project goals

9. plan with "ask" mode, then implement with "agent" mode

10. be specific with prompts. clear instructions get better results

11. maintain todo.md files to track progress

12. use MCP for advanced control

13. adopt test driven development

14. structure code with solid principles

15. tag all necessary files when providing context

16. understand the limitations of ai coding assistance

17. avoid over-reliance on the tool for critical tasks

18. Explain a task to Cursor Agent and have it fill out the todo and details. A transcription app like @WisprFlow or @superwhisperapp is great for this. Takes 2 minutes to describe a full feature and the steps needed. Then let Cursor organise the tasks for you neatly in the .md file based on your voice note.

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

- [MCP Library](https://browsermcp.io)
- [WhatsApp](https://github.com/tulir/whatsmeow)
- [Unity](https://github.com/CoderGamester/mcp-unity)
- [GitHub](https://github.com/github/github-mcp-server)

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


## Twitter tricks
```
Cursor trick: after it generates a plan, before having it implement the plan, say:

"Can we do this with less code? Look for opportunities to make this code more elegant and give me a report with your best ideas."
```

## Twitter agent battle
```
All you need is 2 rules, THAT IS IT! here is how:
create 2 rule files set to "Manual"

agent-1 .mdc:

You are agent-1
you will be chatting with agent-2 to design and build the most interesting python app ever
you will write to agent_1.txt file and read from agent_2.txt file
if you are waiting for a new response write a cli command to wait for 5 seconds and check again
you will repeat this untill the full app is built
you start the conversation

agent-2 .mdc:

You are agent-2
you will be chatting with agent-1 to design and build the most interesting python app ever
you will write to agent_2.txt file and read from agent_1.txt file
if you are waiting for a new response write a cli command to wait for 5 seconds and check again
you will repeat this untill the full app is built
agent-1 will start the convo


create a new agent tab, you should have 2 tabs

assign agent 1 its rule and agent 2 its rule

type "begin" for agent 1 and enter
type "begin" for agent 2 and enter

That is it! and then watch them go to work!
```

## Twitter security
```
Stuff devs always forget (until it's too late):

Security

[ ] Input validation
[ ] Rate limiting
[ ] CORS setup
[ ] HTTPS only
[ ] Env vars not leaked

Auth
[ ] Password hashing (bcrypt)
[ ] JWT expiration
[ ] Email verification
[ ] Forgot password flow

Data
[ ] SQL Injection protection
[ ] Unique constraints in DB
[ ] Backups

Frontend
[ ] No secrets in frontend
[ ] Lazy load heavy stuff
[ ] Prevent XSS

Deploy
[ ] CI pipeline
[ ] Healthcheck routes
[ ] Logging (with levels)
```

## Extensiones
- Git Graph
- GitLens
- GitKraken
- Pylance obvs
- docker
- remote explorer
- alguna para visualizar csv tipo 
- excelviewer
- csvrainbow
- Biome en vez del asqueroso eslint/prettier
- gitlens
- girhub pull requests
- better comments
- y si usas ts, prettier typescript errors

## References
- [Cursor Documentation](https://cursor.sh/docs)
- [Model Context Protocol (MCP)](https://cursor.sh/docs/mcp)
- [Creating and Managing Rules](https://cursor.sh/docs/rules)
- [Keyboard Shortcuts Reference](https://cursor.sh/docs/shortcuts)

- [Awesome CursorRules](https://github.com/PatrickJS/awesome-cursorrules)