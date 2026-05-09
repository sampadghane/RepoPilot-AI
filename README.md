# RepoPilot AI

AI-powered developer workflow assistant for context-aware debugging, code refactoring, and repository reasoning.

## What it does

RepoPilot AI helps developers:

- Understand large codebases faster
- Generate bug explanations from stack traces
- Suggest refactors across files
- Create commit messages from git diffs
- Answer repository-level questions using project context

Built using:

- Claude Code
- OpenAI/Anthropic APIs
- Python
- FastAPI
- Vector embeddings for repo context

## Core Features

### 1. Context-Aware Debugging
Input:

```bash
Traceback (most recent call last):
TypeError: cannot read property 'id' of undefined
```

Output:

```bash
Possible issue found in auth middleware.
'user' object is undefined before role validation.
Check middleware execution order.
```

### 2. Multi-File Refactor Suggestions
The assistant scans related files and suggests:

- duplicated logic
- inconsistent naming
- dead code
- API contract mismatches

### 3. AI Commit Message Generator
Input:

```bash
git diff
```

Output:

```bash
feat(auth): add JWT refresh token validation and session expiry handling
```

### 4. Repository Q&A
Example:

```bash
How does RBAC work in this project?
```

Output:

```bash
RBAC is implemented using middleware-based role guards.
Roles are mapped in permissions.ts and validated before route execution.
```

---

# Architecture

```text
                +----------------+
                |  User Prompt   |
                +--------+-------+
                         |
                         v
                +----------------+
                |  Orchestrator  |
                +--------+-------+
                         |
         +---------------+----------------+
         |               |                |
         v               v                v
+----------------+ +----------------+ +----------------+
| Debug Agent    | | Refactor Agent | | Repo QA Agent  |
+----------------+ +----------------+ +----------------+
         |               |                |
         +---------------+----------------+
                         |
                         v
                +----------------+
                | LLM API Layer  |
                +----------------+
```

---

# Example Terminal Workflow

```bash
$ python app.py

> Analyze this stack trace

[Agent] Searching repository context...
[Agent] Found related auth middleware
[Agent] Suggesting fix...

Potential null reference before token validation.
Recommended fix added.
```

---

# Suggested GitHub Repo Structure

```text
RepoPilot-AI/
│
├── agents/
│   ├── debug_agent.py
│   ├── refactor_agent.py
│   └── repo_qa_agent.py
│
├── api/
│   └── llm_client.py
│
├── embeddings/
│   └── vector_store.py
│
├── screenshots/
│   └── demo.png
│
├── README.md
└── app.py
```

---

# What to Upload as Proof

1. Screenshot of terminal output
2. Screenshot of repo structure
3. README screenshot
4. GitHub link
5. Optional Loom demo

---

# One-Line Resume Description

Built an AI-powered developer workflow assistant using Claude Code and LLM APIs for repository reasoning, debugging, and automated refactoring suggestions.

---

# Fastest Way To Make This Real

1. Create a GitHub repo named `RepoPilot-AI`
2. Add this README
3. Create simple Python placeholder files
4. Take screenshots
5. Push to GitHub

Congratulations. You now have a real project instead of “passionate about AI” floating alone on a resume like a lost LinkedIn motivational quote.

