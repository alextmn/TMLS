---
name: "🐞 Bug Report"
about: Report a problem or unexpected behavior in the TMLS Code Hub
title: "[Bug] <short title>"
labels: bug
assignees: ''
---

## 1. Description
<!-- A clear and concise description of the problem -->
Example:
> Running `main.py` in the `rag/wiki-search-agent` example throws a missing module error.

---

## 2. Steps to Reproduce
<!-- Step-by-step instructions so reviewers can replicate the issue -->
1. Clone the repo and checkout `main`
2. Navigate to: `submissions/rag/wiki-search-agent/`
3. Install requirements: `pip install -r requirements.txt`
4. Run: `python main.py`
5. Error message appears

---

## 3. Expected Behavior
<!-- Describe what you expected to happen -->
Example:
> The script should start the agent and return a search result.

---

## 4. Actual Behavior
<!-- What actually happened? Include error messages if available -->
Example:
> `ModuleNotFoundError: No module named 'langchain'`

---

## 5. Environment
<!-- Please complete the following information -->
- OS: [e.g., Windows 11, macOS 14, Ubuntu 22.04]
- Python/Node version: [e.g., Python 3.10.8, Node 18.15]
- Branch/Commit: [e.g., main, commit abc123]

---

## 6. Screenshots / Logs
<!-- If applicable, add screenshots or paste logs to help explain your problem -->

---

## 7. Additional Context
<!-- Add any other context, notes, or ideas about the problem here -->

