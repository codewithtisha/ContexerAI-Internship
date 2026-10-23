# DevOps Internship — Task 1: Onboarding

**Name:** Tisha Jadav  
**GitHub:** [@codewithtisha](https://github.com/codewithtisha)  
**Submission Repository:** [ContexerAI-Internship](https://github.com/codewithtisha/ContexerAI-Internship)

---

## 1. Introduction

This repository documents my technical onboarding, development environment setup, practical exercises, and troubleshooting experience.

My current focus includes Python environments, Git and GitHub workflows, Docker, automated testing, CI/CD, and AI-assisted development. I aim to understand the tools I use, practise them independently, and learn how to troubleshoot issues systematically.

## 2. Machine and OS

| Item | Details |
|---|---|
| Computer | LG desktop |
| Operating system | Windows 64-bit |
| Terminal | Windows PowerShell |
| Code editor | Visual Studio Code, 64-bit |
| Python environment | Python with `uv`-managed virtual environments |
| Container environment | Docker Desktop with WSL 2 backend |

## 3. Installed Tools and Versions

| Tool | Version | Verification command |
|---|---|---|
| Python | 3.12.9 | `py --version` |
| Git | 2.56.0.windows.2 | `git --version` |
| uv | 0.12.23 | `uv --version` |
| Visual Studio Code | 1.139.1 | `code --version` |
| Claude Code | 2.1.292 | `claude --version` |
| Contexer | 0.54.0 | `contexer --version` |
| Docker | Version to verify | `docker --version` |

*Versions reflect my recorded onboarding environment checks. Docker's exact version still needs verification.*

## 4. Setup and Practical Work

### Python Environment Setup

I used `uv` to create an isolated Python virtual environment for my onboarding work.

```powershell
uv venv
```

The environment was created at `C:\Users\TISHA\Python-Onboarding\.venv`.

PowerShell's execution policy blocked the normal activation script, so I used the environment's Python executable directly:

```powershell
.\.venv\Scripts\python.exe --version
```

### Git and GitHub

I practised creating a branch, updating documentation, committing changes, and opening a pull request.

- **Practice repository:** [Spoon-Knife](https://github.com/octocat/Spoon-Knife) — use your own fork link here if the exercise was completed on your fork.
- **Branch:** `docs/update-readme`
- **Commit:** `d2f34c8`
- **Pull request title:** `Update README with GitHub practice notes`

This exercise helped me understand how branches separate work and how pull requests support review and collaboration.

### Flask, Testing, and CI/CD

I worked on a Flask readiness service to practise application development, automated testing, containerization, and continuous integration.

**Project repository:** [Flask-Readiness](https://github.com/codewithtisha/Flask-Readiness)

The project includes a Flask application, pytest tests, a Dockerfile, and a GitHub Actions workflow. The workflow installs dependencies and runs the test suite when changes are pushed or pull requests are opened.

Example commands used in the project directory:

```powershell
py -m pip install -r requirements.txt
py -m pytest -v
py app.py
```

Docker commands used for the container workflow:

```powershell
docker build -t flask-readiness .
docker run --name flask-readiness-container -p 5000:5000 flask-readiness
```

These commands require the relevant project files and a running Docker engine.

### Contexer Setup

I installed Contexer using `uv` and tested it in a local practice directory.

```powershell
uv tool install contexer
contexer status
contexer install
```

The status and installation commands returned a permission error involving `C:\Users\TISHA\.contexer`. I investigated directory access and inspected the installed permission-handling implementation, but the issue remained unresolved.

## 5. What I Learned

- **Python environments:** Virtual environments isolate dependencies. I learned to run the environment's Python executable directly when PowerShell activation was blocked.
- **Git and GitHub:** Branches provide separate lines of work, commits record changes, and pull requests allow changes to be reviewed.
- **Testing:** Pytest helps verify expected application behaviour and identify regressions.
- **Docker:** Images package application environments, while containers run those images. Port mapping exposes container services through host ports.
- **CI/CD:** GitHub Actions automates checks such as installing dependencies and running tests.
- **Troubleshooting:** Error messages and repeatable diagnostic steps help narrow down problems without assuming an unverified cause.
- **AI-assisted development:** Commands and generated changes should be reviewed, understood, and tested before being trusted.

## 6. Major Problems Encountered

### PowerShell Virtual Environment Activation

**Problem:** PowerShell blocked the virtual environment activation script because of its execution policy.

**Resolution:** I used the virtual environment's Python executable directly instead of changing the system execution policy.

**Learning:** Understanding the restriction helped me continue working without making unnecessary security-related changes.

### Contexer Permission Error

**Problem:** `contexer status` and `contexer install` failed with a permission error involving `C:\Users\TISHA\.contexer`.

**Investigation:** I checked directory properties, tested basic file operations through PowerShell, attempted directory access using Python, and inspected the installed permission-handling code.

**Outcome:** PowerShell file operations worked, but Python's directory-open test returned `PermissionError`. I could not confirm the root cause or complete the setup successfully.

**Learning:** Troubleshooting should distinguish observed results from assumptions. An issue should not be described as resolved until it has been verified.

## 7. Evidence

The [`evidence/`](evidence/) directory contains screenshots supporting the onboarding activities documented here. Evidence will be organised by activity, with descriptive filenames for environment checks, Git workflows, testing, Docker, CI/CD, and Contexer troubleshooting.


