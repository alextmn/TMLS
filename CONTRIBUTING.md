# Contributing to TMLS Code Hub

Thanks for contributing! This repository collects **GenAI best practices, reusable examples, and workflows** reviewed by the TMLS committee. The goals are:

* 🧩 Make contributions easy to add, review, and reuse
* 🔍 Keep projects discoverable and well-documented
* ✅ Uphold quality, security, and ethics standards

> By participating, you agree to follow our **Code of Conduct** (see `CODE_OF_CONDUCT.md`).

---

## 1) Ways to Contribute

* **New example/project** (preferred): add a folder under `submissions/<category>/<project-name>/`
* **Fix or improve** existing content: docs, tests, bug fixes, refactors
* **Add datasets or configs** (small, non-sensitive, reproducible)
* **Open an issue**: bug report, feature request, discussion

---

## 2) Submission Checklist (must have)

Every new submission under `submissions/<category>/<project-name>/` must include:

```
submissions/
  <category>/
    <project-name>/
      README.md              # quick start: what it does & how to run
      description.md         # full write-up (see template below)
      LICENSE                # optional, default MIT unless otherwise required
      _you_files             # source code, other files
```

**Required content in `README.md`:**

* What it is (1–3 sentences)
* Prerequisites and setup
* How to run (commands)
* Example input/output
* Limitations / known issues

**Required content in `description.md`:** use the template below.

---

## 3) Directory & Naming Conventions

* Use **kebab-case** for directory and file names: `java-to-js-llm`, `trading-agent`.
* Categories under `submissions/` (suggested):

  * `agents/`, `rag/`, `prompt-engineering/`, `code-generation/`, `evaluation/`, `ml-pipelines/`, `security-privacy/`
* Keep top-level clean: only repo meta (`README.md`, `CONTRIBUTING.md`, `.github/`, etc.)

---

## 4) Git & PR Workflow

1. **Fork** the repo and create a feature branch:
   `feat/<short-topic>` (e.g., `feat/n8n-twitter-agent`)

2. Add your submission under `submissions/<category>/<project-name>/` and commit using **Conventional Commits**:

   * `feat: add n8n twitter agent`
   * `docs: improve description.md`
   * `fix: handle empty input case`

3. **Open a Pull Request** to `master` with title:
   `New Submission: <project-name>`

4. Fill out the PR template and link any related issues.

5. A **minimum of 1 committee approvals** is required. Review labels:

   * `needs-review` → `changes-requested` or `approved`

6. After approval, a committee member merges the PR.

> **Tip:** Smaller, focused PRs get faster reviews.

---

## 5) Review Standards

The committee evaluates:

* **Clarity & Reproducibility**

  * README quick start works out of the box
  * Scripted or containerized setup (e.g., `requirements.txt`, `Dockerfile`)
  * No hidden steps; commands are copy-paste runnable

* **Quality & Maintainability**

  * Reasonable structure (`src/`, `assets/`)
  * Don't commit any binary files (use other means, like Google Drive, S3, etc)
  * Comments where non-obvious; readable code
  * Tests or at least a sanity check script (preferred)

* **Security, Privacy & Ethics**

  * **No secrets** committed; uses `.env.example`
  * No personal or sensitive data; sample data only
  * If using models, document their **intended use** and **limitations**
  * Disclose any license constraints on code or datasets

* **Originality & Value**

  * Not duplicative; cites sources/inspiration
  * Explains what’s new or why this is useful

---

## 6) Data & Models Policy

* **No large files** (>50 MB) in Git; use small samples. Link to public sources when needed.
* **No private datasets**. If required, provide a script to download from the original source.
* If you include model weights, they must be:

  * Small, openly redistributable, and clearly licensed; *or*
  * Fetched via a script from the official source
* Include citations in `description.md` when appropriate.

---

## 7) Secrets & Config

* Never commit API keys or credentials.
* Provide `.env.example` with placeholder variables and document how to obtain real values.
* If your code loads config, support:

  * `.env` (dotenv)
  * CLI flags or environment variables

---

## 8) Testing & CI

* If possible, add a minimal test:

  * Unit tests (`pytest`, `jest`, etc.), or
  * A **smoke test** script showing end-to-end success
* Aim for deterministic behavior with fixed seeds where relevant.
* We may add CI to run lint/tests on PRs—please keep runtimes short.

---

## 9) Licensing

* The repo is MIT by default. You may include a different license in your project folder **only if required** by dependencies.
* Clearly state any third-party licenses in `description.md`.

---

## 10) Communication & Support

* Use GitHub Issues for bugs and feature requests.
* Use Discussions for design questions or feedback requests.
* Be respectful and constructive—follow the Code of Conduct.

---

## Templates

### A) `description.md` (template)

```markdown
# <Project Title>

## Summary
One paragraph describing what this project does and who it’s for.

## Use Cases
- Bullet list of practical scenarios

## Architecture / Approach
- Short overview (diagram in `assets/` if helpful)
- Key components and data flow
- Model(s) used and why

## Setup & Run
- Prereqs (Python/Node versions, GPU optional, etc.)
- Install commands
- How to run (CLI, notebook, n8n import, etc.)

## Configuration
- Required env vars (see `.env.example`)
- Tunable parameters

## Evaluation (Optional)
- How to validate it works (tests, metrics, golden files)

## Security, Privacy & Ethics
- Data handling notes
- Known risks/limitations and mitigations

## Performance & Limitations
- Expected resource use, latency, constraints

## References & Credits
- Links to papers, repos, blog posts
- Acknowledgements
```

### B) Commit Message Examples (Conventional Commits)

```
feat: add java-to-js-llm migration example
fix: handle empty corpus in rag pipeline
docs: expand README with setup instructions
chore: bump dependencies in agents workspace
```

---

## FAQ

**Q: My contribution doesn’t fit an existing category.**
A: Propose a new one in your PR or open an issue for discussion.

**Q: Can I submit notebooks?**
A: Yes, of course!

**Q: How big can data/assets be?**
A: the commits should be small. If you need to include some files, put them in your Google drive and share the link in `readme.md`.

---

Thanks for helping build a high-quality, reusable TMLS knowledge base!
