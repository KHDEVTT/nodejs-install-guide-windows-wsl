# A Comprehensive Guide to Installing Node.js on Windows Using PowerShell and WSL

## Table of Contents

1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Installing nvm and Node.js using PowerShell](#installing-nvm-and-nodejs-using-powershell)
4. [Installing nvm and Node.js using Windows Subsystem for Linux (WSL)](#installing-nvm-and-nodejs-using-windows-subsystem-for-linux-wsl)
5. [Verifying the Installation](#verifying-the-installation)
6. [Using Node.js](#using-nodejs)
7. [Why Install Node.js in Both Ways?](#why-install-nodejs-in-both-ways)
8. [Conclusion](#conclusion)

## Introduction

### What is Node.js?

Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. It allows you to run JavaScript on the server side, enabling the development of scalable network applications.

### What is nvm?

nvm (Node Version Manager) is a tool that allows you to manage multiple versions of Node.js on your machine. It makes it easy to install, switch, and manage different versions of Node.js.

### What is the Terminal?

The terminal is a text-based interface that allows users to interact with the operating system using commands. On Windows, this can be done using PowerShell or Windows Subsystem for Linux (WSL).

### What is WSL?

WSL (Windows Subsystem for Linux) is a compatibility layer for running Linux binary executables natively on Windows 10 and Windows Server 2019. WSL allows you to use a Linux terminal environment alongside your existing Windows setup.

## Requirements

- A Windows machine running Windows 10 or later
- Windows Terminal installed (can be downloaded from the Microsoft Store)
- Basic familiarity with command-line operations

## Installing nvm and Node.js using PowerShell

### Step 1: Open PowerShell

1. Open Windows Terminal.
2. Click the drop-down arrow next to the new tab button and select `"Windows PowerShell"`.

### Step 2: Download and Install nvm for Windows

1. Download the `nvm-setup.zip` file from the [nvm-windows releases page](https://github.com/coreybutler/nvm-windows/releases).
2. Extract the contents of the zip file.
3. Run the `nvm-setup.exe` installer.

### Step 3: Install the Latest LTS Version of Node.js

1. Open a new PowerShell window.
2. Verify the installation of nvm by typing

```bash
nvm --version
```

3. Install the latest LTS version of Node.js:

```bash
nvm install --lts
```

4. Set the installed LTS version as the default:

```bash
nvm use --lts
```

5. Verify the installation of Node.js and npm (Node Package Manager) by typing:

```bash
node -v
npm -v
```

## Installing nvm and Node.js using Windows Subsystem for Linux (WSL)

### Step 1: Enable WSL and Install a Linux Distribution

1. Open Windows Terminal.
2. Click the drop-down arrow next to the new tab button and select `"Windows PowerShell"`.
3. Enable WSL by typing:

```bash
wsl --install
```

4. Install a Linux distribution (e.g., Ubuntu) from the Microsoft Store.
5. Open the installed Linux distribution.

### Step 2: Install nvm in WSL

1. Update your package list:

```bash
sudo apt update
```

2. Install the required dependencies:

```bash
sudo apt install curl
```

3. Download and install nvm:

- **Note:** Ensure you have [the latest commands](https://github.com/nvm-sh/nvm).

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.0/install.sh | bash

```

4. Load nvm into your shell session:

```bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

### Step 3: Install the Latest LTS Version of Node.js using nvm in WSL

1. Verify the installation of nvm by typing:

```bash
nvm --version
```

2. Install the latest LTS version of Node.js:

```bash
nvm install --lts
```

3. Set the installed LTS version as the default:

```bash
nvm use --lts
```

4. Verify the installation of Node.js and npm by typing:

```bash
node -v
npm -v
```

## Verifying the Installation

After following the installation steps for either PowerShell or WSL, you should verify that Node.js and npm are correctly installed.

1. Open a terminal window (PowerShell or WSL).
2. Check the Node.js version:

```bash
Check the npm version:

```

3. Check the npm version:

```bash
npm -v
```

If both commands return version numbers, the installation was successful.

## Using Node.js

To start using Node.js, you can create a simple JavaScript file and run it with Node.js.

### Step 1: Create a JavaScript File

1. Open a terminal window (PowerShell or WSL).

2. Create a new file named `app.js`:

```bash
echo console.log('Hello, Node.js!'); > app.js
```

### Step 2: Run the JavaScript File

1. Run the file using Node.js:

```bash
node app.js
```

You should see the output:

```bash
Hello, Node.js!
```

## Why Install Node.js in Both Ways?

### Development and Testing Across Environments

- **Consistency Across Platforms:** If you're developing applications that will be deployed on both Windows and Linux servers, having Node.js installed in both PowerShell and WSL allows you to test your applications in environments similar to your production servers.
- **Cross-Platform Compatibility:** Certain Node.js modules or dependencies might behave differently on Windows versus Linux. Testing in both environments helps identify and resolve these issues early in the development process.

### Leveraging Linux Tools and Ecosystem

- **Access to Linux Tools:** WSL allows you to use Linux-based tools and utilities, which can be beneficial for certain development workflows. For instance, you might prefer using bash scripts, Linux-based package managers, or other command-line tools that are not natively available on Windows.
- **Scripting and Automation:** Many developers find bash scripting more powerful and flexible for automation tasks. Having Node.js in WSL allows you to write and run these scripts natively.

### Flexibility and Preference

- **Developer Preference:** Some developers are more comfortable working in a Linux environment due to familiarity with the tools and command-line interface. WSL provides a native-like Linux environment within Windows.
- **Windows Integration:** Other developers might prefer the integration and tools available in the Windows ecosystem, such as PowerShell, Visual Studio Code, and other Windows-based development tools.

### Learning and Experimentation

- **Learning Opportunity:** Using both environments can be a great way to learn and understand the differences between Windows and Linux. It helps in becoming proficient in both operating systems, which is valuable for a well-rounded development skill set.
- **Experimentation:** Having both environments available allows you to experiment with different workflows and tools to determine what works best for your specific needs.

### Docker and Containerization

- **Docker Compatibility:** If you are using Docker, WSL provides a better environment for running Docker containers natively. Many Docker images are based on Linux distributions, and having Node.js installed in WSL can facilitate seamless integration and testing with Docker.

### Example Use Cases

- **Web Development:** You might develop a Node.js application in PowerShell and test it in a Linux environment via WSL to ensure it works seamlessly on a Linux server.
- **CI/CD Pipelines:** Setting up CI/CD pipelines that run tests in both Windows and Linux environments ensures that your application behaves consistently across different deployment environments.
- **Package Management:** Using `npm` or `yarn` within WSL might provide different results due to filesystem behaviors and case sensitivity. Testing in both environments helps catch these differences.

## Conclusion

Choosing between PowerShell and WSL depends on your specific needs and preferences. For simplicity and integration with Windows tools, PowerShell is recommended. For a development environment closer to Linux production servers and access to powerful Linux tools, WSL is a better choice. Both methods provide robust ways to install and manage Node.js on your Windows machine.

By following this comprehensive guide, you can ensure that you have a flexible and versatile development environment that caters to a wide range of scenarios and preferences.

## Author

**[Karen @ KHDEVTT](https://khdevtt.com)**

- [Follow on X](https://x.com/khdevtt)

---

If you have any questions, suggestions, or feedback, feel free to reach out!
