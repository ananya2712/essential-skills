# HTML Code Walkthrough Prompt

Use this prompt when a user asks for a single-page website that explains a codebase to someone who does not know the project.

```text
Inspect the code folder I provide and create a single-page index.html that explains the project to someone unfamiliar with it.

Include:
- Overview: what the application does and who uses it.
- Technology stack: main frameworks, libraries, and storage.
- Folder structure: important directories and their responsibilities.
- How it works: trace one core user action from the interface through the backend and database, where applicable.
- Key files: entry points and files that contain important business logic.
- How to run it: setup, configuration, and commands verified against the repository.
- Limitations: incomplete features and uncertainties supported by the code.

Base explanations on the actual source. Clearly label anything you cannot verify. Put relevant file paths beside explanations. Use plain language and explain technical terms when needed. Do not expose secrets.

Create one self-contained index.html with embedded CSS and no external dependencies. Use a white background, dark text, clear headings, and a small table of contents that links to page sections. Make the page usable on desktop and mobile. Do not add animations, decorative graphics, dashboards, or unnecessary interactions.

Do not modify application code. The page must help me understand the project and explain it during a code walkthrough.
```

Before delivery, check every project claim against source files. Check setup commands against files such as `README.md`, `compose.yaml`, `docker-compose.yml`, `package.json`, `pyproject.toml`, and `.env.example`, when present. If you cannot run a command, label it as source-verified but not run. If you run it, report the result. Do not present an assumption as a verified fact.
