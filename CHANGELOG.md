# Changelog

All notable changes to **NOVA Terminal** are documented in this file.

## [1.0.3] - 2026-10-29

### Added

- **C/C++ Development Support:** Added workflows for compiling and running C and C++ programs using compatible GCC and G++ compilers.
- **Node.js Project Setup:** Added project setup capabilities to help developers create a Node.js project structure and get started faster.
- **Git Integration:** Added command support for common Git workflows, including repository initialization, status checks, staging, commits, branches, remotes, and other version-control operations.
- **File Management:** Expanded developer workflows for creating, reading, editing, searching, and managing files and directories.
- **System Information Tools:** Added or expanded commands for viewing system information, checking system health, monitoring processes, and inspecting disk information.
- **Developer Utilities:** Expanded command support for common development and project-management tasks.

### Improved

- **Error Handling:** Improved handling and presentation of command execution errors to help developers identify and troubleshoot problems.
- **Subprocess Execution:** Improved workflows for executing supported external commands and programs.
- **Node.js Workflow:** Improved support for running Node.js applications and managing npm-based workflows.
- **Python Workflow:** Improved Python execution and package-management workflows.
- **Watch Mode:** Improved file-monitoring and automatic-restart workflows for supported programs.
- **Command Help:** Expanded command descriptions and usage guidance to make NOVA easier to use.
- **Developer Experience:** Improved terminal usability and consolidated common development tasks into one environment.

### NOVA AI

- Continued support for AI-powered error explanations through the Gemini API.
- Support for AI Mode controls using `nova ai on`, `nova ai off`, and `nova ai status`.
- Support for configuring an API key using `nova ai set-key`.
- Error analysis can explain possible causes and suggest potential fixes when the AI integration is configured and available.

### Documentation

- Updated `README.md` with clearer installation instructions and feature descriptions.
- Expanded `FEATURES.md` to document developer-focused functionality.
- Updated `COMMANDS.md` with command descriptions and examples.
- Expanded `TROUBLESHOOTING.md` with installation, runtime, Git, compiler, Watch Mode, and AI troubleshooting guidance.

## [1.0.2] - 2026-10-22

### Added
- **NOVA AI Mode:** Added AI-powered error explanation using the Gemini API.
- **AI Status Management:** Added `nova ai on`, `nova ai off`, and `nova ai status`.
- **API Key Configuration:** Added `nova ai set-key` to configure the user's Gemini API key.
- **Error Analysis:** Added explanations of errors, possible causes, and suggested fix commands.

## [1.0.1]

### Added
- **NOVA Watch:** Added the `nova watch <filename>` command to monitor a file for changes.
- **Automatic Restart:** Added automatic restart behavior for supported monitored programs.
- **Error Detection:** Added error output during the watch workflow.

## [1.0.0]

### Added
- **Colorful CLI:** Introduced a colorful terminal interface.
- **Python Execution:** Added support for running Python code.
- **Node.js Execution:** Added support for running Node.js code.
- **Package Management:** Added support for `pip` and `npm` workflows.
- **Compile and Run Workflow:** Added compilation and execution workflows supported by the relevant runtimes and tools.

## [0.1.0]

### Release
- Initial development release of NOVA Terminal.
- Established the foundation for the terminal project.

---

## Versioning

NOVA Terminal follows the `MAJOR.MINOR.PATCH` versioning format:

- **MAJOR:** Breaking changes.
- **MINOR:** New backward-compatible features.
- **PATCH:** Backward-compatible bug fixes and improvements.

## Project Information

- **Project:** NOVA Terminal
- **Developer / Publisher:** Shivexa
- **PyPI Package:** `shivexa-nova-terminal`
- **PyPI:** https://pypi.org/project/shivexa-nova-terminal/
- **GitHub:** https://github.com/Shivexa/nova-terminal
