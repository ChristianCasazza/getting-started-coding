# Getting Started with Local Development

Welcome! This guide will help you set up your computer with a baseline for running most common applications written in Python, JavaScript, and TypeScript—all within Visual Studio Code (VSCode). By following these steps, you’ll install VSCode, configure a development environment (including WSL for Windows users), install uv (a fast Python package manager), Node.js, and Git, and connect to your GitHub account.

## 1. Install Visual Studio Code

### Download VSCode
- Visit [VSCode Download](https://code.visualstudio.com/download).
- Choose your operating system (Windows, macOS, or Linux) and download the installer.

### Install VSCode
- Open the downloaded installer and follow the on-screen instructions.
- When prompted, you can enable the options to add the VSCode executable to your PATH (on Windows), which makes it easier to open VSCode from the command line.

### Launch VSCode
- After installation, open VSCode.
- Take a moment to familiarize yourself with the interface.

---

## 2. (Optional) Using Windows Subsystem for Linux (WSL) on Windows

If you’re on Windows, you can benefit from using the Windows Subsystem for Linux (WSL). WSL provides a full Linux environment inside Windows, which can make development more seamless for certain projects.

### Check your Windows version
- You need Windows 10 (version 2004 or higher) or Windows 11 for WSL 2.

### Install WSL
1. Open PowerShell (Run as Administrator) or Command Prompt (Admin).
2. Enter the command:

   ```powershell
   wsl --install
   ```

   This command will enable the required components and download the latest Linux distribution. After it completes, you may need to restart your computer.

### Set up your Linux distribution
- After your computer restarts, you’ll be prompted to configure the new Linux environment (choose a username and password, etc.).

### Use VSCode with WSL
- Install the **Remote - WSL** extension in VSCode (search for it in the Extensions panel).
- Then, you can open a folder in WSL by clicking the green “><” button in the bottom-left corner of VSCode and selecting **Remote-WSL: New Window**.

> **Note:** Using WSL is optional but can simplify working with Linux-based tools on a Windows machine.

---

## 3. Install uv

**uv** is an extremely fast Python package manager that simplifies creating and managing Python projects. We’ll install it first to ensure our Python environment is ready to go.

### Install uv

Instead of downloading executables manually, you should copy and paste the following command into your terminal, which will automatically download and install uv:
For Linux:

```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Windows Powershell:
```sh
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```


### What This Command Does:
- `curl -LsSf`: Downloads the install script quietly and safely.
- `| sh`: Runs the script in your shell, installing uv automatically.

### If You Encounter Issues:
- If you run the command and get an error, copy and paste your terminal output into ChatGPT for troubleshooting.

---

## 4. Test Your uv Installation

### Open the Terminal in VSCode
- In VSCode, look at the top menu and select **Terminal > New Terminal**, or press:
  - **Windows/Linux:** `Ctrl` + `` ` `` (Control + backtick)
  - **macOS:** `Command` + `` ` ``

### Run the command:
```sh
uv
```

#### Expected output:
If uv was installed correctly, you should see a help message that starts with:

```sh
An extremely fast Python package manager.

Usage: uv [OPTIONS] <COMMAND>

Commands:
  run      Run a command or script
  init     Create a new project
  ...
  help     Display documentation for a command
```

#### If you get an error:
- Copy and paste the exact error message into ChatGPT and explain you’re having problems using uv.
- ChatGPT can help troubleshoot your specific error message.

If uv displays its usage information without an error, congratulations! You’re all set to work with Python in your local environment.

---

## 5. Install Node.js and nvm

To develop JavaScript (JS) or TypeScript (TS) applications, you’ll need Node.js. A popular way to manage multiple Node.js versions is by using **nvm** (Node Version Manager).

### Install nvm (Linux/macOS)
1. Open your terminal (WSL on Windows, Terminal on macOS/Linux).
2. Follow the install instructions on the [nvm GitHub repository](https://github.com/nvm-sh/nvm).

### Use nvm to install Node.js
Once nvm is installed, you can install Node.js by running:

```sh
nvm install --lts
```

This command installs the latest **Long-Term Support (LTS)** version of Node.js.

### For Windows users
- While nvm also exists for Windows (**nvm-windows**), many people find it simpler to just use the official Node.js installer if you do not plan on switching Node versions frequently.
- If you do use **nvm-windows**, follow the steps provided in that repository’s documentation.

### Verify Node.js installation
```sh
node -v
```
This should print the version of Node.js you installed.


#### Again, if you get an error:
- Copy and paste the exact error message into ChatGPT and explain you’re having problems using uv.
- ChatGPT can help troubleshoot your specific error message.


---

## 6. Create a Free GitHub Account

GitHub is a platform that hosts your code online and helps with version control and collaboration.

### Sign up
- Go to [GitHub](https://github.com) and create a free account if you don’t already have one.

### Explore GitHub
- Once you have an account, you can create repositories, explore others’ code, and collaborate on projects.

---

## 7. Install Git on Your Computer

Git is the version control system that integrates with GitHub to sync your local code with your repositories online.

### Install Git
- **Windows**: Download the installer from [git-scm.com](https://git-scm.com/download/win) and follow the prompts.
- **macOS**: Install Git via Homebrew (`brew install git`) or Xcode Command Line Tools.
- **Linux**: Use your distribution’s package manager:
  - Ubuntu/Debian: `sudo apt-get install git`
  - Fedora: `sudo dnf install git`

### Verify Git installation
```sh
git --version
```
You should see the installed version number.

---

## 8. Sign In to GitHub from the Command Line

### Configure Git locally
Open your VSCode terminal and set up your user name and email:

```sh
git config --global user.name "Your Name"
git config --global user.email "YourEmail@example.com"
```

### Authenticate with GitHub

#### **HTTPS Method:**
When you first push or pull from a GitHub repository via HTTPS, Git will prompt you for your GitHub username and password (or personal access token).

#### **SSH Method (recommended):**
1. Generate an SSH key pair on your computer (if you haven’t already) with:

   ```sh
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

2. Copy the public key (the contents of `~/.ssh/id_ed25519.pub`) and add it to your GitHub account under **Settings > SSH and GPG keys**.

Now you can clone and push without entering a username/password each time.

---

## Summary

### Congratulations! You’ve installed and set up:
- **VSCode** (your primary code editor)
- **WSL** (optional for Windows users)
- **uv** (for Python projects)
- **Node.js and nvm** (for JavaScript and TypeScript projects)
- **Git and GitHub** (for version control and collaborating on code)

You’re now ready to start coding with a solid local development environment. If you run into any issues, check the error messages and ask ChatGPT for help. See you on the other side!
