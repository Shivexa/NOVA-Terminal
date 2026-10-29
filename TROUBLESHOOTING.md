# NOVA Terminal — Troubleshooting Guide

**Package:** `shivexa-nova-terminal`  
**Publisher:** Shivexa  
**Installation:** Python / pip  
**Purpose:** Diagnose and resolve common NOVA Terminal installation, command execution, configuration, and runtime issues.

---

## Table of Contents

1. [Installation Issues](#1-installation-issues)
2. [NOVA Command Not Found](#2-nova-command-not-found)
3. [Python Execution Issues](#3-python-execution-issues)
4. [Node.js and npm Issues](#4-nodejs-and-npm-issues)
5. [Git Command Issues](#5-git-command-issues)
6. [Watch Mode Issues](#6-watch-mode-issues)
7. [AI Mode and Gemini API Issues](#7-ai-mode-and-gemini-api-issues)
8. [File and Directory Command Issues](#8-file-and-directory-command-issues)
9. [C and C++ Compilation Issues](#9-c-and-c-compilation-issues)
10. [Subprocess Execution Errors](#10-subprocess-execution-errors)
11. [System Information Command Issues](#11-system-information-command-issues)
12. [Updating NOVA Terminal](#12-updating-nova-terminal)
13. [Windows-Specific Issues](#13-windows-specific-issues)
14. [Debugging Checklist](#14-debugging-checklist)
15. [Getting More Help](#15-getting-more-help)

---

## 1. Installation Issues

### Problem: Package installation fails

**Possible causes**

- Internet connection problems.
- An outdated pip version.
- An incompatible Python environment.
- Permission restrictions.
- Package installation into a different Python environment.

**Try this:**

```bash
python --version
python -m pip --version
python -m pip install --upgrade pip
python -m pip install shivexa-nova-terminal
```

On Windows, you can also use the Python launcher:

```powershell
py --version
py -m pip install --upgrade pip
py -m pip install shivexa-nova-terminal
```

### Problem: Permission denied

If your system reports a permission error, first check whether you are installing into the intended Python environment.

A virtual environment is usually a safer choice than installing packages globally.

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\activate
```

Activate it on Linux or macOS:

```bash
source .venv/bin/activate
```

Then install NOVA:

```bash
python -m pip install shivexa-nova-terminal
```

### Problem: pip cannot find the package

Check the package name carefully:

```bash
python -m pip install shivexa-nova-terminal
```

If installation still fails, check your internet connection, pip output, and the package's availability on PyPI. Do not assume every installation failure is caused by NOVA itself.

---

## 2. NOVA Command Not Found

### Problem: `nova` is not recognized

Example on Windows:

```text
'nova' is not recognized as an internal or external command
```

Possible causes:

- NOVA was installed into a different Python environment.
- Python's Scripts directory is missing from PATH.
- Installation did not finish successfully.
- The terminal was not restarted after installation.

### Step 1: Verify installation

```bash
python -m pip show shivexa-nova-terminal
```

If the package is not found, install it in the Python environment you intend to use.

### Step 2: Check the Python environment

```bash
python --version
python -m pip --version
```

On Windows:

```powershell
py -m pip show shivexa-nova-terminal
```

### Step 3: Reopen the terminal

Close and reopen your terminal, then try:

```bash
nova
```

### Step 4: Check the Scripts directory

On Windows, find the Python environment's Scripts directory and confirm that it is available in PATH.

If you use a virtual environment, activate that environment before running NOVA.

**Important:** Use the launcher and command syntax supported by your installed NOVA version. Do not assume a command is available just because it appears in documentation.

---

## 3. Python Execution Issues

### Problem: Python program does not run

**Possible causes**

- Python is not installed.
- Python is unavailable in PATH.
- The filename or path is incorrect.
- The script contains a syntax or runtime error.
- A required Python dependency is missing.

### Check Python

```bash
python --version
```

On Windows, try:

```powershell
py --version
```

### Check the file

Make sure your file exists in the current directory:

```bash
dir
```

On Linux or macOS:

```bash
ls
```

Then run the file using the Python command supported by your NOVA version.

For comparison, you can test the script directly:

```bash
python main.py
```

On Windows:

```powershell
py main.py
```

### Problem: SyntaxError or runtime error

Example:

```text
SyntaxError: invalid syntax
```

This normally indicates a problem in the Python source code.

Check the line number in the traceback and review the code around that location. A `SyntaxError`, `NameError`, `ModuleNotFoundError`, or similar exception does not automatically mean NOVA is broken.

### Problem: ModuleNotFoundError

Example:

```text
ModuleNotFoundError: No module named 'requests'
```

Install the missing dependency in the same Python environment used to run your script:

```bash
python -m pip install requests
```

Replace `requests` with the actual missing module's package name when necessary.

---

## 4. Node.js and npm Issues

### Problem: Node.js or npm is not recognized

Check whether Node.js and npm are installed:

```bash
node --version
npm --version
```

If either command is unavailable, install Node.js from the official website:

https://nodejs.org/

Restart your terminal after installation and check the versions again.

### Problem: JavaScript file fails

For a basic Node.js script, test it directly:

```bash
node app.js
```

Check the filename, working directory, required modules, and error output.

### Problem: Cannot find module

Example:

```text
Error: Cannot find module 'express'
```

If the project has a valid `package.json`, install its dependencies from the project directory:

```bash
npm install
```

If a particular package is genuinely missing from the project, install it using npm:

```bash
npm install express
```

### Problem: Project starts but exits immediately

Check:

- Whether the entry-point file is correct.
- Whether `package.json` contains the expected scripts.
- Whether the application encounters an exception.
- Whether the server or process is designed to remain running.

Test the application directly with Node.js before investigating NOVA-specific behavior.

---

## 5. Git Command Issues

### Problem: Git is not recognized

Check Git:

```bash
git --version
```

If Git is unavailable, install it from the official website:

https://git-scm.com/downloads

Restart your terminal after installation.

### Problem: Git commands fail inside NOVA

Try the same command in your normal terminal:

```bash
git status
```

If it also fails there, the problem is likely related to Git installation, repository configuration, or the current directory.

### Problem: Not a Git repository

Example:

```text
fatal: not a git repository (or any of the parent directories): .git
```

Move into the correct project directory:

```bash
cd your-project
git status
```

If you are creating a new repository, initialize it deliberately:

```bash
git init
```

### Problem: Git asks for identity

Configure your commit identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Use the name and email you want associated with your commits.

### Problem: Push or authentication fails

Check the remote configuration:

```bash
git remote -v
```

Verify your repository URL and authentication method. Do not paste access tokens, passwords, or private SSH keys into public issues.

**Note:** NOVA's ability to forward Git commands depends on the installed implementation and whether Git is available on the system.

---

## 6. Watch Mode Issues

### Problem: `nova watch filename` does not restart the program

Possible causes:

- The filename or path is incorrect.
- The file was not saved.
- The program exits before a change can be processed.
- The monitored file is not supported by the current implementation.
- The installed NOVA version uses different command syntax.

### Troubleshooting steps

1. Confirm that the file exists.
2. Run the program normally first.
3. Start Watch Mode using the syntax supported by your installed version.
4. Save the monitored file after making a change.
5. Read the terminal output for errors.
6. Confirm whether the implementation watches the file itself or a wider set of project files.

If the program reports an error after restarting, fix that error before investigating the restart mechanism.

**Note:** Automatic restart behavior depends on the actual Watch Mode implementation, monitored file types, and process-handling logic.

---

## 7. AI Mode and Gemini API Issues

### Problem: AI error explanation does not work

Possible causes:

- AI Mode is disabled.
- The API key is missing or invalid.
- The configured model is unavailable.
- The network connection is failing.
- The API has reached a quota or rate limit.
- The provider has a temporary service issue.

### Step 1: Check AI Mode

```bash
nova ai status
```

If AI Mode is disabled and your installed version supports it, enable it:

```bash
nova ai on
```

### Step 2: Configure the API key

If supported by your installed version:

```bash
nova ai set-key
```

Follow the prompts provided by NOVA.

### Step 3: Inspect the actual API error

Different errors require different solutions:

| Error category | Recommended action |
|---|---|
| Invalid API key | Verify the key and its provider configuration. |
| Quota exceeded | Check the provider's quota and billing limits. |
| Rate limit | Wait before retrying and avoid repeated rapid requests. |
| Network error | Check your connection and any proxy or firewall settings. |
| Service unavailable | Retry later if the provider reports a temporary outage. |
| Model unavailable | Verify the configured model and API compatibility. |

### Security warning

Never publish your API key in GitHub issues, screenshots, public logs, or support messages.

If your key is exposed, revoke or rotate it through the relevant provider. Avoid printing secret values while debugging.

**Important:** AI features require a working provider integration and valid configuration. Do not assume an API failure means the entire NOVA Terminal has crashed.

---

## 8. File and Directory Command Issues

### Problem: File or directory cannot be found

Check the current working directory:

```bash
```

Use NOVA's supported location and listing commands, if available, to confirm where you are and whether the file exists.

### Problem: File creation or deletion fails

Possible causes:

- The path is incorrect.
- The current user lacks permission.
- The file is open or locked by another application.
- A directory is not empty.
- The operation is restricted by the operating system.

### Recommended checks

1. Verify the exact path and filename.
2. Confirm that the target directory exists.
3. Check read/write permissions.
4. Make sure you are operating in the intended project directory.
5. Read the full error message before retrying.

**Safety reminder:** Commands that delete files or directories can cause data loss. Verify the target path before running destructive operations.

---

## 9. C and C++ Compilation Issues

### Problem: GCC or G++ is not recognized

Check the compiler:

```bash
gcc --version
g++ --version
```

If either command is unavailable, install a compatible C/C++ compiler for your operating system and configure PATH if required.

### Problem: Compilation fails

For C:

```bash
gcc main.c -o main
```

For C++:

```bash
g++ main.cpp -o main
```

Read the compiler output carefully. Errors such as a missing header, undefined reference, or syntax error usually require changes to the source code or build configuration.

**Windows note:** The executable output and run command may differ depending on the compiler and shell. For example, GCC-based Windows environments commonly produce `main.exe`.

Test compilation directly in your system terminal to determine whether the issue is compiler-related or NOVA-related.

---

## 10. Subprocess Execution Errors

NOVA may use subprocess-based execution for supported external commands and programs.

### Problem: A command starts but the program fails

Possible causes:

- The executable is missing.
- Command arguments are incorrect.
- The working directory is wrong.
- A required file or dependency is missing.
- The launched program returns a non-zero exit code.

### Recommended checks

1. Read the complete error output.
2. Confirm that the executable is installed.
3. Verify the working directory and file path.
4. Check whether the command requires quotes around paths containing spaces.
5. Run the equivalent command directly in your normal terminal.
6. Inspect the exit code if NOVA exposes it.

### Example: Path contains spaces

A file path such as:

```text
C:\My Projects\app\main.py
```

may need correct quoting or argument handling, depending on the command and shell.

### Understand the source of the failure

A subprocess error does not always mean NOVA itself has crashed. The launched program, missing executable, invalid argument, or system environment may be responsible.

---

## 11. System Information Command Issues

### Problem: System information commands fail

Commands such as `system_info`, `health_check`, `process_info`, `disk_info`, `ip_info`, or `live_monitor` may depend on the implementation, operating system, available permissions, or external utilities.

### Recommended checks

- Confirm that the command exists in your installed version.
- Check whether the command requires an optional dependency.
- Verify operating-system compatibility.
- Inspect permission-related errors.
- Try an equivalent built-in operating-system command where appropriate.

### Problem: Some information is missing

Not every system exposes the same metrics or process details. Certain values may require permissions or platform-specific support.

Missing information does not necessarily indicate a NOVA installation problem.

---

## 12. Updating NOVA Terminal

### Problem: The old version is still installed

Upgrade the package:

```bash
python -m pip install --upgrade shivexa-nova-terminal
```

On Windows:

```powershell
py -m pip install --upgrade shivexa-nova-terminal
```

Check the installed package details:

```bash
python -m pip show shivexa-nova-terminal
```

### Problem: The updated version does not appear

1. Confirm which Python environment pip is using.
2. Upgrade NOVA in that same environment.
3. Restart the terminal.
4. Check whether a different Python installation or virtual environment provides the `nova` command.
5. Compare the installed version with the release you intended to install.

If needed, use the appropriate Python launcher consistently for both installation and verification.

---

## 13. Windows-Specific Issues

### Problem: Commands work in one terminal but not another

Different terminals may load different PATH values or activate different virtual environments.

Try:

```powershell
where.exe python
where.exe pip
where.exe nova
where.exe node
where.exe git
```

A command may return no result if that executable is not available through the current PATH.

### Problem: Access denied

Check directory permissions and whether the target file is being used by another process. Avoid running every command as administrator; use elevated permissions only when genuinely necessary.

### Problem: Terminal does not recognize a newly installed program

Close and reopen the terminal after installing Python, Node.js, Git, or a compiler. If the problem persists, verify the PATH configuration.

---

## 14. Debugging Checklist

Before reporting a bug, follow this checklist:

- [ ] Confirm that NOVA is installed.
- [ ] Check the installed package version.
- [ ] Verify that the required runtime or executable is installed.
- [ ] Confirm the current working directory and file path.
- [ ] Run the failing program directly outside NOVA.
- [ ] Read the complete error message or traceback.
- [ ] Check whether the command is supported by your installed version.
- [ ] Verify relevant environment variables and configuration.
- [ ] Remove secrets and private information from any logs you share.
- [ ] Reproduce the issue using the smallest possible example.

### Useful diagnostic commands

```bash
python --version
python -m pip --version
python -m pip show shivexa-nova-terminal
node --version
npm --version
git --version
```

Run only the checks relevant to your issue. Node.js, npm, Git, and C/C++ compilers are optional dependencies unless a particular workflow requires them.

---

## 15. Getting More Help

If the issue remains unresolved, report it through the project's official support or issue-tracking channel.

Include:

- Operating system and version.
- Python version.
- NOVA Terminal package version.
- The command you ran.
- The complete error message, with sensitive information removed.
- Expected behavior and actual behavior.
- Steps to reproduce the issue.
- Whether the same command works outside NOVA.

Do not include passwords, API keys, access tokens, personal data, or confidential files.

For security vulnerabilities, follow the reporting instructions in `SECURITY.md`.

---

## Related Documentation

- `README.md` — Project overview and installation.
- `INSTALLATION.md` — Installation and setup instructions.
- `FEATURES.md` — NOVA Terminal features.
- `COMMANDS.md` — Supported commands and examples.
- `SECURITY.md` — Security guidance and vulnerability reporting.
- `CHANGELOG.md` — Release history and changes.

---

**NOVA Terminal by Shivexa**

Build, run, and manage your development workflows from one terminal environment.

*Documentation note: Troubleshooting steps describe common environments and failure patterns. Exact command availability, AI configuration, Watch Mode behavior, and platform support depend on the installed NOVA Terminal version and its actual implementation.*
