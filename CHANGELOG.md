# Changelog

All notable changes to **NOVA Terminal** are documented in this file.

## [1.0.2] - 2026-10-22

### Added
- **NOVA AI Mode:** Added AI-powered error explanation using the Gemini API.
- **AI Status Management:** Added commands to turn `nova ai on` or `nova ai off` and check its status for `nova ai status`.
- **API Key Configuration:** Added `nova ai set-key` to configure the user's Gemini API key.
- **Error Analysis:** When AI Mode is enabled, NOVA AI provides:
  - **Explanation:** Explains the error in understandable language.
  - **Cause:** Identifies the possible reason behind the error.
  - **Fix Command:** Suggests a command to help fix the issue.

## [1.0.1]

### Added
- **NOVA Watch:** Added the `nova watch <filename>` command to monitor a file for changes.
- **Automatic Restart:** Automatically restarts the monitored program when its file changes, reducing the need for manual restarts.
- **Error Detection:** Displays detected execution errors in the terminal during the watch workflow.

## [1.0.0]

### Added
- **Colorful CLI:** Introduced an attractive, colorful terminal interface.
- **Package Management:** Added support for managing Python packages with `pip` and Node.js packages with `npm`.
- **Python Execution:** Added support for running Python code.
- **Node.js Execution:** Added support for running Node.js code.
- **Compile and Run Workflow:** Added code compilation and execution workflows supported by the relevant language runtimes.

## [0.1.0]

### Release
- Initial development release of NOVA Terminal.
- Established the foundation for the terminal project.

---

## Versioning

NOVA Terminal follows the `MAJOR.MINOR.PATCH` versioning format:

- **MAJOR:** Major changes that may break compatibility.
- **MINOR:** New features and functionality.
- **PATCH:** Bug fixes and smaller improvements.

## Project Information

- **Project:** NOVA Terminal
- **Developer:** Shivexa
- **PyPI Package:** `shivexa-nova-terminal`
- **PyPI:** https://pypi.org/project/shivexa-nova-terminal/
- **GitHub:** https://github.com/Shivexa/nova-terminal
