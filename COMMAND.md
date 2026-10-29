# NOVA Terminal --- Command Reference

**NOVA Terminal** is a command-line tool by **Shivexa** for terminal
workflows, file management, project execution, system inspection, and
developer tools.

> **Command syntax note:** Examples below follow the command names
> provided for NOVA Terminal. If a command in your installed version
> uses interactive prompts or a different argument order, follow the
> prompt or check that version's help output.

## Contents

-   [Installation](#installation)
-   [1. Internal Commands](#1-internal-commands)
-   [2. Navigation Commands](#2-navigation-commands)
-   [3. File Management Commands](#3-file-management-commands)
-   [4. Search and Text Commands](#4-search-and-text-commands)
-   [5. NOVA AI Commands](#5-nova-ai-commands)
-   [6. System Information Commands](#6-system-information-commands)
-   [7. Project Commands](#7-project-commands)
-   [8. Python Commands](#8-python-commands)
-   [9. Node.js Commands](#9-nodejs-commands)
-   [10. C and C++ Commands](#10-c-and-c-commands)
-   [11. pip Commands](#11-pip-commands)
-   [12. npm Commands](#12-npm-commands)
-   [13. Other External Commands](#14-other-external-commands)
-   [14. git Commands]
-   [Troubleshooting](#troubleshooting)

## Installation

Install NOVA Terminal with pip:

``` bash
python -m pip install shivexa-nova-terminal
```

If `pip` is available directly, you can also use:

``` bash
pip install shivexa-nova-terminal
```

## Internal vs. External Commands

-   **Internal commands** are built into NOVA Terminal and are handled
    by its own command system.
-   **External commands** are executed by, or depend on, tools installed
    on your computer---such as Python, Node.js, pip, npm, GCC, and G++.
-   Some NOVA commands may launch an external tool internally. The
    command's behavior depends on your installed NOVA Terminal version
    and system configuration.

## 1. Internal Commands

These commands are built into NOVA Terminal.

  Command    Purpose                               Example
  ---------- ------------------------------------- ----------
  `helpme`   Show the NOVA Terminal help message   `helpme`
  `wipe`     Clear the terminal screen             `wipe`
  `say`      Print a welcome greeting              `say`
  `close`    Close the NOVA Terminal shell         `close`

### Example

``` text
helpme
```

Use `helpme` whenever you need to review the commands available in your
installed version.

## 2. Navigation Commands

  Command   Purpose                           Example
  --------- --------------------------------- ----------------
  `where`   Show the current directory path   `where`
  `show`    List files and folders            `show`
  `go`      Change the current directory      `go myproject`

### Example workflow

``` text
show
go myproject
where
go ..
```

This lists the current directory, enters `myproject`, displays the
current path, and then moves to the parent directory.

## 3. File Management Commands

  Command     Purpose                    Example
  ----------- -------------------------- ----------------------------
  `newdir`    Create a directory         `newdir projects`
  `deldir`    Delete a directory         `deldir projects`
  `newfile`   Create a file              `newfile app.py`
  `delfile`   Delete a file              `delfile app.py`
  `rdfile`    Read a file's contents     `rdfile app.py`
  `putfile`   Write content to a file    `putfile app.py`
  `clone`     Copy a file or directory   `clone app.py app_copy.py`
  `erase`     Erase a file's contents    `erase app.py`

### Example workflow

``` text
newdir demo
go demo
newfile hello.py
rdfile hello.py
```

For commands such as `putfile`, your version may ask for content
interactively. Follow its prompt if it does.

> **Warning:** `deldir`, `delfile`, and `erase` can remove data.
> Double-check the target before running them.

## 4. Search and Text Commands

  Command    Purpose                              Example
  ---------- ------------------------------------ ---------------------
  `seek`     Search for text inside a file        `seek hello app.py`
  `first`    Display the first lines of a file    `first app.py`
  `last`     Display the last lines of a file     `last app.py`
  `count`    Count lines, words, and characters   `count app.py`
  `locate`   Find files or directories by name    `locate app.py`

### Example

``` text
seek hello app.py
first app.py
last app.py
count app.py
locate app.py
```

The examples show the intended usage. Confirm argument order with your
installed version if a command prompts for input or reports invalid
arguments.

## 5. NOVA AI Commands

Use these commands to manage NOVA AI features and configuration.

  -----------------------------------------------------------------------
  Command                 Purpose                 Example
  ----------------------- ----------------------- -----------------------
  `nova ai on`            Enable NOVA AI          `nova ai on`

  `nova ai off`           Disable NOVA AI         `nova ai off`

  `nova ai status`        Check the current AI    `nova ai status`
                          status                  

  `nova ai set-key`       Set the API key used by `nova ai set-key`
                          NOVA AI                 
  -----------------------------------------------------------------------

### Example workflow

``` text
nova ai status
nova ai on
nova ai status
```

To configure an API key, run:

``` text
nova ai set-key
```

Follow the prompt shown by your installed version. **Do not paste API
keys into public issues, commits, screenshots, or documentation.** If
the tool supports it, store the key in an environment variable or a
secure local configuration file.

## 6. System Information Commands

These commands provide information about your computer and its current
state.

  -----------------------------------------------------------------------
  Command                 Purpose                 Example
  ----------------------- ----------------------- -----------------------
  `ip_info`               Display IP/network      `ip_info`
                          information             

  `live_monitor`          Show live system        `live_monitor`
                          monitoring information  

  `system_info`           Display system          `system_info`
                          information             

  `health_check`          Run a system health     `health_check`
                          check                   

  `process_info`          Display process         `process_info`
                          information             

  `disk_info`             Display disk/storage    `disk_info`
                          information             
  -----------------------------------------------------------------------

### Example

``` text
system_info
health_check
disk_info
process_info
ip_info
live_monitor
```

`live_monitor` may keep updating until you stop it. Use the exit key or
stop method shown by the command if it runs continuously.

## 7. Project Commands

### `nova watch`

Watch a file during development.

``` bash
nova watch app.py
```

Use this when you want NOVA's watch functionality for a file. Whether it
automatically reruns a program or only monitors changes depends on the
implementation.

### `nova start`

Start a backend project or server using a supported entry-point file.

``` bash
nova start server.py
```

Another example:

``` bash
nova start app.py
```

Make sure you are in the correct project directory and that the required
dependencies are installed. Supported project types and startup behavior
depend on your NOVA Terminal version.

## 8. Python Commands

### Run a Python file

Use NOVA's Python runner:

``` text
run python app.py
```

Or use the Python interpreter directly:

``` bash
python app.py
```

On some Windows installations, the launcher may be:

``` bash
py app.py
```

### Start a Python backend

For a project with `server.py` as its entry point:

``` text
nova start server.py
```

Or, when the project is designed to run directly with Python:

``` bash
python server.py
```

For framework-based applications, use the startup command specified by
the project. For example, a FastAPI project may use Uvicorn if it is
installed and configured:

``` bash
python -m uvicorn main:app --reload
```

### Execute Python code directly

Use `python forwrite` followed by Python code:

``` text
python forwrite print("Hello from Python")
```

This is the documented command pattern supplied for NOVA Terminal. If
your version opens an editor or prompts for code instead, follow its
prompt.

## 9. Node.js Commands

### Run a JavaScript file with Node.js

Use NOVA's Node command:

``` text
start node app.js
```

Or call Node.js directly:

``` bash
node app.js
```

### Start a Node.js backend

For a backend with `server.js` as the entry point:

``` text
nova start server.js
```

Or run it directly:

``` bash
node server.js
```

For a project that defines a start script in `package.json`, use:

``` bash
npm start
```

### Execute JavaScript code directly

Use `node for` followed by JavaScript code:

``` text
node for console.log("Hello from Node.js")
```

This example follows the command pattern provided. If your version
accepts code interactively, enter the code when prompted.

## 10. C and C++ Commands

### Compile a C program

``` text
gcc hello.c
```

Run the default output on Linux/macOS:

``` bash
./a.out
```

On Windows with MinGW GCC, the output is commonly `a.exe`:

``` powershell
.\a.exe
```

For an explicit output filename:

``` bash
gcc hello.c -o hello
```

### Compile a C++ program

``` text
g++ hello.cpp
```

For an explicit output filename:

``` bash
g++ hello.cpp -o hello
```

Run the output using the filename produced by your compiler and
operating system.

> `gcc` and `g++` require a compatible C/C++ compiler to be installed
> and available on your PATH. The NOVA examples show the command names
> provided by NOVA Terminal; confirm whether your implementation
> automatically runs the compiled program or only compiles it.

## 11. pip Commands

`pip` is Python's package installer. These are common pip commands that
can be run through an external-command interface when supported by your
NOVA Terminal setup.

  Task                               Command
  ---------------------------------- -----------------------------------
  Install a package                  `pip install requests`
  Install a specific version         `pip install requests==2.32.3`
  Upgrade a package                  `pip install --upgrade requests`
  Uninstall a package                `pip uninstall requests`
  Show package details               `pip show requests`
  List installed packages            `pip list`
  List outdated packages             `pip list --outdated`
  Freeze installed packages          `pip freeze`
  Save dependencies                  `pip freeze > requirements.txt`
  Install from a requirements file   `pip install -r requirements.txt`
  Check dependency compatibility     `pip check`
  Display pip version                `pip --version`
  Display pip help                   `pip --help`

### Recommended examples

Install a package:

``` bash
python -m pip install requests
```

Install project dependencies:

``` bash
python -m pip install -r requirements.txt
```

Check installed packages:

``` bash
python -m pip list
```

Using `python -m pip` helps target the pip associated with the selected
Python interpreter.

## 12. npm Commands

`npm` is the package manager commonly used with Node.js. These are
common npm commands.

  Task                               Command
  ---------------------------------- -------------------------------------
  Initialize a project               `npm init`
  Initialize with default settings   `npm init -y`
  Install project dependencies       `npm install`
  Install a package                  `npm install express`
  Install a development dependency   `npm install --save-dev nodemon`
  Install a package globally         `npm install --global package-name`
  Uninstall a package                `npm uninstall express`
  Update dependencies                `npm update`
  List installed packages            `npm list`
  List top-level packages            `npm list --depth=0`
  Run the project's start script     `npm start`
  Run a custom package script        `npm run dev`
  Display npm version                `npm --version`
  Display npm help                   `npm help`
  Audit dependencies                 `npm audit`
  Try automatic audit fixes          `npm audit fix`

### Recommended example: create a Node.js backend

``` bash
mkdir my-backend
cd my-backend
npm init -y
npm install express
```

Create a `server.js` file, then run it:

``` bash
node server.js
```

If your `package.json` defines a `start` script, you can also run:

``` bash
npm start
```

Only use `npm run dev` if your `package.json` defines a `dev` script.

## 13. Other External Commands

These commands depend on the corresponding tools being installed and
available in your system's PATH.

  Tool      Example              Purpose
  --------- -------------------- -----------------------
  Python    `python --version`   Check Python version
  Node.js   `node --version`     Check Node.js version
  npm       `npm --version`      Check npm version
  pip       `pip --version`      Check pip version
  GCC       `gcc --version`      Check GCC version
  G++       `g++ --version`      Check G++ version
  Git       `git --version`      Check Git version

#14. Git Commands — NOVA Terminal

NOVA Terminal supports Git-related commands to help developers manage repositories, track code changes, create commits, and work with branches directly from the terminal.

> **Note:** The commands below document standard Git commands. Use only the commands implemented in NOVA Terminal.

## 1. `git init`

**Description:** Initializes a new Git repository in the current directory.

**Syntax:**
```bash
git init
```

**Example:**
```bash
nova> git init
```

**Use case:** Start tracking a new project with Git.

---

## 2. `git status`

**Description:** Displays the current state of the repository, including modified, staged, and untracked files.

**Syntax:**
```bash
git status
```

**Example:**
```bash
nova> git status
```

**Use case:** Check which files have changed before committing.

---

## 3. `git add`

**Description:** Adds file changes to the staging area so they can be included in the next commit.

**Syntax:**
```bash
git add <filename>
git add .
```

**Examples:**
```bash
nova> git add main.py
nova> git add .
```

**Use case:** Stage a specific file or all eligible changes in the current directory.

---

## 4. `git commit`

**Description:** Saves the staged changes as a new commit in the repository history.

**Syntax:**
```bash
git commit -m "commit message"
```

**Example:**
```bash
nova> git commit -m "Add new features"
```

**Use case:** Record a meaningful snapshot of your code changes.

---

## 5. `git log`

**Description:** Displays the repository's commit history.

**Syntax:**
```bash
git log
git log --oneline
```

**Examples:**
```bash
nova> git log
nova> git log --oneline
```

**Use case:** Review previous commits and understand the project's history.

---

## 6. `git diff`

**Description:** Shows differences between file versions, working-tree changes, and staged changes.

**Syntax:**
```bash
git diff
git diff --staged
```

**Examples:**
```bash
nova> git diff
nova> git diff --staged
```

**Use case:** Review code changes before committing them.

---

## 7. `git branch`

**Description:** Lists existing branches or creates a new branch.

**Syntax:**
```bash
git branch
git branch <branch-name>
```

**Examples:**
```bash
nova> git branch
nova> git branch feature-login
```

**Use case:** Organize development work into separate branches.

---

## 8. `git checkout`

**Description:** Switches branches or restores files, depending on the options used.

**Syntax:**
```bash
git checkout <branch-name>
git checkout -b <branch-name>
```

**Examples:**
```bash
nova> git checkout main
nova> git checkout -b feature-login
```

**Use case:** Switch to an existing branch or create and switch to a new branch.

---

## 9. `git switch`

**Description:** Switches between Git branches. It is a modern alternative to using `git checkout` for branch switching.

**Syntax:**
```bash
git switch <branch-name>
git switch -c <branch-name>
```

**Examples:**
```bash
nova> git switch main
nova> git switch -c feature-dashboard
```

**Use case:** Navigate between development branches.

---

## 10. `git merge`

**Description:** Integrates changes from one branch into the currently checked-out branch.

**Syntax:**
```bash
git merge <branch-name>
```

**Example:**
```bash
nova> git switch main
nova> git merge feature-login
```

**Use case:** Merge completed feature work into the main development branch.

---

## 11. `git clone`

**Description:** Creates a local copy of an existing remote repository.

**Syntax:**
```bash
git clone <repository-url>
```

**Example:**
```bash
nova> git clone https://github.com/user/project.git
```

**Use case:** Download a project from GitHub or another Git hosting service.

---

## 12. `git remote`

**Description:** Manages remote repository connections.

**Syntax:**
```bash
git remote -v
git remote add origin <repository-url>
```

**Examples:**
```bash
nova> git remote -v
nova> git remote add origin https://github.com/user/project.git
```

**Use case:** View configured remotes or connect a local repository to a remote repository.

---

## 13. `git fetch`

**Description:** Downloads updates and references from a remote repository without automatically merging them into the current branch.

**Syntax:**
```bash
git fetch
git fetch origin
```

**Examples:**
```bash
nova> git fetch
nova> git fetch origin
```

**Use case:** Check for remote updates before integrating them.

---

## 14. `git pull`

**Description:** Fetches remote updates and integrates them into the current branch according to the configured Git behavior.

**Syntax:**
```bash
git pull
git pull origin main
```

**Examples:**
```bash
nova> git pull
nova> git pull origin main
```

**Use case:** Update your local branch with remote changes.

---

## 15. `git push`

**Description:** Uploads local commits to a remote repository.

**Syntax:**
```bash
git push
git push origin main
git push -u origin main
```

**Examples:**
```bash
nova> git push
nova> git push origin main
nova> git push -u origin main
```

**Use case:** Publish your local commits to a remote repository.

---

## 16. `git reset`

**Description:** Moves the current branch reference or changes the staging state, depending on the selected option.

**Syntax:**
```bash
git reset <filename>
git reset --soft HEAD~1
git reset --hard HEAD~1
```

**Examples:**
```bash
nova> git reset main.py
nova> git reset --soft HEAD~1
```

**Use case:** Unstage files or adjust recent commits.

**Warning:** `git reset --hard` can permanently discard uncommitted changes. Use it carefully.

---

## 17. `git stash`

**Description:** Temporarily stores uncommitted changes so you can work on something else.

**Syntax:**
```bash
git stash
git stash list
git stash pop
```

**Examples:**
```bash
nova> git stash
nova> git stash list
nova> git stash pop
```

**Use case:** Temporarily save your current work without creating a commit.

---

## 18. `git rm`

**Description:** Removes tracked files from the working tree and stages their removal.

**Syntax:**
```bash
git rm <filename>
```

**Example:**
```bash
nova> git rm old_file.py
```

**Use case:** Remove a tracked file from the repository.

---

## 19. `git mv`

**Description:** Moves or renames a tracked file and stages the change.

**Syntax:**
```bash
git mv <old-name> <new-name>
```

**Example:**
```bash
nova> git mv old_name.py new_name.py
```

**Use case:** Rename or move files while keeping Git's change tracking.

---

## 20. `git tag`

**Description:** Creates or lists tags, commonly used to mark release versions.

**Syntax:**
```bash
git tag
git tag <tag-name>
```

**Examples:**
```bash
nova> git tag
nova> git tag v1.0.0
```

**Use case:** Mark important milestones or software releases.

---

## Complete Git Workflow Example

The following sequence demonstrates a typical workflow for a project connected to a remote repository.

```bash
nova> git init
nova> git status
nova> git add .
nova> git commit -m "Initial commit"
nova> git branch
nova> git remote add origin https://github.com/user/project.git
nova> git push -u origin main
```

**Before running the example:**
- Ensure Git is installed and available in your system's PATH.
- Replace the sample repository URL with your actual repository URL.
- Ensure your current branch is named `main`, or substitute its actual name.
- Configure Git identity if required:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## Important Notes

- These are standard Git commands and examples, not a guarantee that every command is implemented as a native NOVA Terminal command.
- If NOVA Terminal supports direct command execution, use the examples with its prompt. Otherwise, execute them in the underlying system terminal.
- Commands that modify repository history or delete files should be used carefully.
- Git operations that access remote repositories may require network connectivity and authentication.



External commands are not necessarily built into NOVA Terminal. Their
availability depends on your operating system, installed tools, and how
NOVA Terminal dispatches commands.

## Troubleshooting

-   **Command not recognized:** Check the spelling and confirm that the
    command exists in your NOVA Terminal version.
-   **Python not found:** Install Python and make sure it is available
    on your PATH.
-   **Node or npm not found:** Install Node.js, which normally includes
    npm, and reopen the terminal.
-   **Compiler not found:** Install GCC/G++ or an appropriate compiler
    toolchain.
-   **File not found:** Run `where` and `show` to check the current
    directory.
-   **Package installation fails:** Check the internet connection,
    Python/Node version compatibility, and package error output.
-   **Project fails to start:** Confirm the entry-point filename,
    dependencies, environment variables, and project configuration.

## Safety Notes

-   Do not publish API keys, tokens, passwords, or other secrets.
-   Review commands before running them, especially commands that delete
    files or change system configuration.
-   Install packages only from sources you trust.
-   Commands and options may differ by operating system and NOVA
    Terminal release.

## About NOVA Terminal

**Developed by Shivexa**

-   Website: https://shivexa.in
-   GitHub: https://github.com/Shivexa/
-   PyPI: https://pypi.org/project/shivexa-nova-terminal/

------------------------------------------------------------------------

If you find an issue or a command behaves differently in your release,
please report the NOVA Terminal version and the command you ran in the
project's GitHub repository.
