NOVA Terminal — Troubleshooting Guide

This guide helps you identify and resolve common issues when installing and using NOVA Terminal.

Package: "shivexa-nova-terminal"
Publisher: Shivexa
Installation: Python pip

---

Table of Contents

- "Installation Issues" (#1-installation-issues)
- "NOVA Command Not Found" (#2-nova-command-not-found)
- "Python Execution Issues" (#3-python-execution-issues)
- "Node.js and npm Issues" (#4-nodejs-and-npm-issues)
- "Watch Mode Issues" (#5-watch-mode-issues)
- "AI Mode and Gemini API Issues" (#6-ai-mode-and-gemini-api-issues)
- "Subprocess Execution Errors" (#7-subprocess-execution-errors)
- "Updating NOVA Terminal" (#8-updating-nova-terminal)
- "Getting More Help" (#9-getting-more-help)

---

1. Installation Issues

Problem: Package installation fails

Possible causes

- Internet connection problems.
- An outdated pip version.
- Python environment or permission issues.

Try this:

python -m pip install --upgrade pip
python -m pip install shivexa-nova-terminal

If your system uses the "py" launcher on Windows, you can also try:

py -m pip install shivexa-nova-terminal

If the problem continues, read the complete error message before trying other fixes.

---

2. NOVA Command Not Found

Problem: "nova" is not recognized

Possible causes

- The package was installed into a different Python environment.
- The Python Scripts directory is not in PATH.
- Installation did not complete successfully.

Check the installation:

python -m pip show shivexa-nova-terminal

On Windows, try running the command through Python's Scripts directory or configure the correct Scripts directory in PATH.

Then reopen your terminal and try:

nova

Use the launcher and command syntax supported by your installed NOVA version.

---

3. Python Execution Issues

Problem: Python program fails to run

Possible causes

- Python is not installed or is unavailable in PATH.
- The filename or file path is incorrect.
- The program contains a syntax or runtime error.

Check Python:

python --version

On Windows, you can also try:

py --version

Check your script:

Make sure the file exists in the current directory and run it using the supported NOVA command.

If the script produces an error, inspect the traceback. Fix the actual Python error rather than assuming the terminal itself is broken.

---

4. Node.js and npm Issues

Problem: Node.js or npm command fails

Possible causes

- Node.js is not installed.
- Node.js or npm is not available in PATH.
- The JavaScript file contains an error.

Check the installations:

node --version
npm --version

If either command is unavailable, install Node.js from the official website:

https://nodejs.org/

Restart your terminal after installation and check the versions again.

---

5. Watch Mode Issues

Problem: "nova watch filename" does not restart the program

Possible causes

- The filename or path is incorrect.
- The watched file was not saved.
- The program exits or fails before a change can be processed.
- The current NOVA version does not support the expected syntax.

Try these checks:

1. Confirm that the file exists.
2. Run the program normally first.
3. Start Watch Mode using the syntax supported by your installed version.
4. Save the file and inspect the terminal output.

If the program reports an error after restarting, resolve that error first.

Note: Automatic restart behaviour depends on the Watch Mode implementation and the file being monitored.

---

6. AI Mode and Gemini API Issues

Problem: AI error explanation fails

Possible causes

- AI Mode is disabled.
- The API key is missing or invalid.
- The configured model or API is temporarily unavailable.
- Network problems, rate limits, or API quota restrictions.

Check AI Mode:

nova ai status

If appropriate, enable it:

nova ai on

Configure your own Gemini API key using the supported command:

nova ai set-key

Follow the prompts provided by NOVA.

If a request fails, inspect the actual API error. For example, a temporary service-unavailable response may require retrying later, while an invalid-key response requires checking your key.

Security warning: Never share your API key in GitHub issues, screenshots, public logs, or support messages. If a key is exposed, revoke or rotate it through the relevant provider.

---

7. Subprocess Execution Errors

Problem: A command starts but the program fails

NOVA uses subprocess-based execution for supported external commands and programs.

Possible causes

- The executable is missing.
- The command arguments are incorrect.
- The program exits with a non-zero exit code.
- A required file or dependency is missing.

Recommended checks:

1. Read the complete error output.
2. Confirm that the required executable is installed.
3. Verify the working directory and file path.
4. Try the equivalent command directly in your normal terminal.
5. Check the exit code, if NOVA exposes it.

A subprocess error does not always mean NOVA itself has crashed; the launched program may be the source of the failure.

---

8. Updating NOVA Terminal

Problem: The old version is still installed

Upgrade the package:

python -m pip install --upgrade shivexa-nova-terminal

Check the installed package version:

python -m pip show shivexa-nova-terminal

If the reported version is not what you expected, verify which Python environment is running pip and which environment provides the "nova" command.

---

9. Getting More Help

If your issue remains unresolved, report it through the official NOVA Terminal support channel.

Include:

- Operating system and version.
- Python version.
- NOVA Terminal package version.
- The command you ran.
- The complete error message, with private information removed.
- Steps to reproduce the issue.

Do not include passwords, API keys, personal data, or confidential files.

For security vulnerabilities, follow the reporting instructions in "SECURITY.md" (SECURITY.md).

---

NOVA Terminal by Shivexa

For installation instructions, see "INSTALLATION.md" (INSTALLATION.md).
For supported commands, see "COMMANDS.md" (COMMANDS.md).
