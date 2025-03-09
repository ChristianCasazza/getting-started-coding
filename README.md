# Getting Started with Local Development

Welcome! This guide will help you set up your computer with a baseline for running most common applications written in Python, JavaScript, and TypeScript—all within Visual Studio Code (VSCode). By following these steps, you’ll install VSCode, configure a development environment (including WSL for Windows users), install uv (a fast Python package manager), install Bun (a fast JavaScript/Typescript package and runtime manager), and Git, and connect to your GitHub account.

- **VSCode** (Free and simple code interface)
- **WSL** (To make life easier for Windows users)
- **uv** (To make life easier with Python projects)
- **Bun** (To make life easier with JavaScript and TypeScript projects)
- **Git and GitHub** (for built in version control and collaborating on code with others)

Everything in this guide is a one time setup that then forever sets up your laptop to run software applications for free locally.

## 1. Install VSCode(Visual Studio Code)

### Download VSCode
- Visit [VSCode Download](https://code.visualstudio.com/download).
- Choose your operating system (Windows, macOS, or Linux) and download the installer.

### Install VSCode
- Open the downloaded installer and follow the on-screen instructions.
- When prompted, you can enable the options to add the VSCode executable to your PATH (on Windows), which makes it easier to open VSCode from the command line. I would just select checking any box that mentions PATH.

### Launch VSCode
- After installation, open VSCode.
- Take a moment to familiarize yourself with the interface. 
- Notice on the left side the explorer button. This is where you can click to open repositories of code.
- At the top of the screen are different tabs like **File**
- Clicking **File** and then **New Window** will open a fresh VSCode screen

---

## 2. (Optional) Using Windows Subsystem for Linux (WSL) on Windows

If you use a Mac or Linux laptop, skip to 3.

If you’re on Windows, it is **highly** recommend to conduct all coding in WSL, the Windows Subsystem for Linux (WSL). WSL provides a full Linux environment inside Windows. Linux is an open source operating system that can run in an isolated environment on a windows laptop. Using Linux makes it a lot easier for developers work with open source software. It also comes with really nice quality of life benefits for coding. 

### Check your Windows version
- You need Windows 10 (version 2004 or higher) or Windows 11 for WSL 2.

### Install WSL
1. Open your computer search bar and enter powershell
2. When **Windows PowerShell** is shown, right click on it and select **Run as Administrator**, and click **yes**. 
3. Enter the command:

   ```powershell
   wsl --install
   ```

   This command will enable the required components and download the latest Linux distribution. After it completes, try to open and close VSCode. It is possible you may need to restart you computer.

### Set up your Linux distribution
- After your computer restarts, you’ll be prompted to configure the new Linux environment (choose a username and password, etc.).
- Choose a local username and password you will remember, and save a copy. This will be your login for your WSL coding experiance.

### Use VSCode with WSL
- Install the **Remote - WSL** extension in VSCode (search for it in the Extensions panel).
- Then, you can open a folder in WSL by clicking the Status Bar button in the bottom-left corner of VSCode, underneath the gear icon. Then, select **Connect to WSL**. By default it should open Ubuntu, but if that doesn't work, you could also click **Connect to WSL using Distro**, and so **Ubuntu** is the first option to select.

> **Note:** Using WSL is optional but highly recomended for making your life easier for developing while using a Windows machine. 

---

## 3. Install uv for python code

**uv** is an extremely fast Python package manager that simplifies creating and managing Python projects. We’ll install it first to ensure our Python environment is ready to go. uv makes working with python both faster and simpler.

### Install uv

In VSCode, at the top of the screen, you will see an option that says **Terminal**. Then, you should click the button, and then select **New Terminal**. Then, copy and paste the following commands to install uv. You can double check they are the correct scripts by going to the official uv site, maintained by the company astral.

[Install uv](https://docs.astral.sh/uv/getting-started/installation/#standalone-installer)

```macOS, WSL, and Linux
curl -LsSf https://astral.sh/uv/install.sh | sh
```

If you are using Windows and also not using WSL.

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
- In VSCode, look at the top menu and select **Terminal > New Terminal**, then:

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

## 5. Install Bun for JS and TS code

[Bun](https://bun.sh/docs) is an extremely fast runtime and package manager that simplifies creating and managing JavaScript (JS) or TypeScript (TS) projects. We’ll install it first to ensure our Js/TS environment is ready to go. Bun makes working with JS and TS code both faster and simpler.


### Install Bun

In VSCode, at the top of the screen, you will see an option that says **Terminal**. Then, you should click the button, and then select **New Terminal**. Then, copy and paste the following commands to install bun. You can double check they are the correct scripts by going to the official bun site.

[Install Bun](https://bun.sh/docs/installation)

```macOS, WSL, and Linux
curl -fsSL https://bun.sh/install | bash 
```

If you are using Windows and also not using WSL.

Windows Powershell:
```sh
powershell -c "irm bun.sh/install.ps1|iex"
```

### What This Command Does:
- `curl -LsSf`: Downloads the install script quietly and safely.
- `| sh`: Runs the script in your shell, installing uv automatically.

### If You Encounter Issues:
- If you run the command and get an error, copy and paste your terminal output into ChatGPT for troubleshooting.

---

## 6. Test Your Bun Installation

### Open the Terminal in VSCode
- In VSCode, look at the top menu and select **Terminal > New Terminal**

### Run the command:
```sh
bun
```

#### Expected output:
If Bun was installed correctly, you should see a help message that starts with something like this:

```sh
Bun is a fast JavaScript runtime, package manager, bundler, and test runner. (1.2.4+fd9a5ea66)

Usage: bun <command> [...flags] [...args]

Commands:
  run       ./my-script.ts       Execute a file with Bun
            lint                 Run a package.json script
  test                           Run unit tests with Bun
  x         prettier             Execute a package binary (CLI), installing if needed (bunx)
  repl                           Start a REPL session with Bun
  exec                           Run a shell script directly with Bun

  install                        Install dependencies for a package.json (bun i)
```

#### Again, if you get an error:
- Copy and paste the exact error message into ChatGPT and explain you’re having problems installing and using bun.
- ChatGPT can help troubleshoot your specific error message.

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

If you are using a mac, it may automatically ask to install developer tools if this is your first time running code.

---

## 8. Create a Free GitHub Account

GitHub is a platform that hosts your code online and helps with version control and collaboration.

### Sign up
- Go to [GitHub](https://github.com) and create a free account if you don’t already have one.

### Explore GitHub
- Once you have an account, you can create repositories, explore others’ code, and collaborate on projects.

---

## 9. Sign In to GitHub from the Command Line

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
- **VSCode** (Simple and free code interface)
- **WSL** (To make life easier for Windows users)
- **uv** (To make life easier with Python projects)
- **Bun** (To make life easier with JavaScript and TypeScript projects)
- **Git and GitHub** (for built in version control and collaborating on code with others)

You’re now ready to start coding with a solid local development environment. If you run into any issues, check the error messages and ask ChatGPT for help. See you on the other side!
