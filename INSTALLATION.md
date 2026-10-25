# NOVA Terminal — Installation Guide

**By Shivexa | Windows Installation Guide**

Welcome to NOVA Terminal! This guide will help you install and start using NOVA in three ways: from the official website, with Python/pip, or directly in Visual Studio Code.

> **Choose one method.** You do not need to complete all three.

## 1. Install from the Official Website

1. Visit the official NOVA Terminal website and open the **Download** page.
2. Download the Windows version provided there.
3. Follow the instructions for the file you downloaded:
   - **Installer (`.exe`):** Double-click it and follow the installation steps shown on screen.
   - **Portable application (`.exe`):** Move it to a permanent folder (for example, `C:\Tools\NOVA\`) and double-click it to launch.
   - **Install command:** If the website shows a pip command instead of an app download, follow [Method 2](#2-install-from-pypi-using-pip).
4. Open NOVA and try a basic command.

**Optional — run a portable NOVA executable from any terminal:** If your download includes a `nova.exe` command-line launcher, add the **folder containing that executable** to Windows PATH using the steps in [Set PATH on Windows](#set-path-on-windows). If your download is a graphical app with no command-line launcher, use its shortcut instead.

> The exact download button and installation experience depend on the version offered on the official website. Download only from the official Shivexa source.

## 2. Install from PyPI Using pip

This method installs NOVA as a Python package.

### Step 1 — Install Python

1. Go to https://www.python.org/downloads/windows/.
2. Download and install a compatible Python version (Python 3.10 or newer).
3. During installation, enable **Add Python to PATH** if the installer offers it.
4. Close and reopen Command Prompt or PowerShell.

Check Python:

```powershell
python --version
```

Check pip:

```powershell
python -m pip --version
```

If `python` is not recognized, try `py --version` and use `py -m pip` in the commands below, or reinstall Python with PATH enabled.

### Step 2 — Install NOVA

Open **Command Prompt** or **PowerShell** and run:

```powershell
python -m pip install shivexa-nova-terminal
```

Wait for the installation to finish.

### Step 3 — Launch NOVA

```powershell
nova
```

If NOVA opens, installation is complete!

### Step 4 — If `nova` Is Not Recognized

You may see:

```text
'nova' is not recognized as an internal or external command
```

This usually means the Python **Scripts** folder is not on PATH.

**Find the correct Scripts folder:**

```powershell
python -c "import sysconfig; print(sysconfig.get_path('scripts'))"
```

If pip installed NOVA into your *user* location (you may see `Defaulting to user installation`), find that Scripts folder with:

```powershell
python -m site --user-base
```

Append `\Scripts` to the printed location. For example, if the output is:

```text
C:\Users\YourName\AppData\Roaming\Python\Python313
```

The Scripts folder is:

```text
C:\Users\YourName\AppData\Roaming\Python\Python313\Scripts
```

Use the actual path from **your** computer. Confirm that `nova.exe` exists in the folder before adding it to PATH.

### Set PATH on Windows

1. Press **Windows + S** and search **Edit environment variables for your account**.
2. Open it and select **Path** under **User variables**.
3. Click **Edit** → **New**.
4. Paste the folder path containing `nova.exe` (not the `nova.exe` file itself).
5. Click **OK** on all open windows.
6. **Close and reopen** Command Prompt, PowerShell and VS Code terminals.
7. Run:

```powershell
nova
```

> You normally need to add the Scripts folder only once. Do not replace or delete the other entries in PATH.

## 3. Install from VS Code

Use this method if you want to launch NOVA inside Visual Studio Code.

### Step 1 — Install VS Code

Download Visual Studio Code from https://code.visualstudio.com/ and open it.

### Step 2 — Install the NOVA Extension

1. Click the **Extensions** icon on the left, or press `Ctrl + Shift + X`.
2. Search for **NOVA Terminal** by **Shivexa**.
3. Open the extension listing and click **Install**.
4. If prompted, click **Reload** or restart VS Code.

**Alternative: install from a `.vsix` file**

1. Download the official NOVA `.vsix` extension file.
2. In VS Code, open **Extensions**.
3. Click the **...** menu → **Install from VSIX...**.
4. Select the downloaded `.vsix` file.
5. Reload VS Code if requested.

### Step 3 — Open NOVA

1. Find the **NOVA** button in the VS Code status bar.
2. Click **NOVA** to launch the terminal.
3. On first launch, allow the extension to complete its setup if prompted. An internet connection and a compatible Python installation may be needed because the extension installs or updates the NOVA Python package.
4. Wait for NOVA to appear in the integrated terminal.

**Important:** When launching NOVA through the extension's **NOVA** button, you normally do **not** need to type a separate pip installation command. If you want to type `nova` manually in other terminals, follow Method 2 and the PATH instructions.

## 4. Check Your Installation

Try these basic commands in NOVA:

```text
helpme
```

To exit, use NOVA's supported exit command or close the terminal tab/window.

If a command is unavailable in your installed version, check the version-specific command documentation.

## 5. Update NOVA

**PyPI installation:**

```powershell
python -m pip install --upgrade shivexa-nova-terminal
```

**VS Code extension:** Open **Extensions**, find **NOVA Terminal**, and choose **Update** if an update is offered. The extension may also update its Python package when launched.

**Website installation:** Download the latest official release and follow its provided update instructions.

## 6. Uninstall NOVA

**PyPI:**

```powershell
python -m pip uninstall shivexa-nova-terminal
```

**VS Code:** Go to **Extensions** → **NOVA Terminal** → **Uninstall**. If you also installed the Python package separately and want to remove it, run the pip uninstall command above.

**Website:** Use Windows **Installed apps** for an installed application, or delete the portable file if it was a portable download.

## 7. Common Problems & Fixes

| Problem | What to do |
|---|---|
| `python` is not recognized | Install Python and enable PATH, then restart the terminal. Try `py --version`. |
| `No module named pip` | Repair or reinstall Python with pip enabled. |
| `nova` is not recognized | Follow the [PATH steps](#set-path-on-windows) and reopen the terminal. |
| NOVA button not visible in VS Code | Check that the extension is installed and enabled; reload VS Code. |
| First VS Code launch takes time | Wait for setup to finish; check your internet connection. |
| Permission error during pip installation | Try `python -m pip install --user shivexa-nova-terminal`. |
| An older NOVA version opens | Run the upgrade command, then reopen your terminal. |

## 8. Useful Links

- [NOVA Terminal on PyPI](https://pypi.org/project/shivexa-nova-terminal/)
- [Python Downloads](https://www.python.org/downloads/)
- [Visual Studio Code](https://code.visualstudio.com/)

---

**You're ready to use NOVA Terminal!** Choose the installation method that fits your workflow and start coding.

*© Shivexa — NOVA Terminal*
