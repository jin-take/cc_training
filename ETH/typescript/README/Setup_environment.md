# Setting Up the Development Environment by TypeScript
TypeScript Setup Guide (Windows & macOS)

This guide explains how to set up Node.js and TypeScript using asdf and create a virtual environment on both Windows and macOS. The guide assumes that Homebrew is already installed.

## Prerequisites
- Homebrew is installed

## Steps

### 1. Install asdf

#### Windows
1. **Install Windows Subsystem for Linux (WSL)**
   - Open PowerShell as an administrator and run the following command:
     ```sh
     wsl --install
     ```
   - After restarting, complete the Ubuntu setup.

2. **Install asdf**
   - Open WSL (Ubuntu) and run the following commands:
     ```sh
     git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.9.0
     echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc
     echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc
     source ~/.bashrc
     ```

#### macOS
1. **Install asdf using Homebrew**
   - Open Terminal and run the following command:
     ```sh
     brew install asdf
     echo -e '\n. $(brew --prefix asdf)/asdf.sh' >> ~/.zshrc
     source ~/.zshrc
     ```

### 2. Install Node.js

1. **Add asdf plugin**
   - Open Terminal (macOS) or WSL (Windows) and run:
     ```sh
     asdf plugin-add nodejs https://github.com/asdf-vm/asdf-nodejs.git
     ```

2. **Install Node.js**
   - Install the desired version of Node.js. Here, we'll install the latest LTS version.
     ```sh
     asdf install nodejs lts
     asdf global nodejs lts
     ```

3. **Check Node.js version**
   - Verify the installed version of Node.js.
     ```sh
     node -v
     ```

### 3. Install TypeScript

1. **Install TypeScript**
   - Open Terminal (macOS) or WSL (Windows) and run:
     ```sh
     npm install -g typescript
     ```

2. **Install ts-node**
   - To directly execute TypeScript files, install ts-node.
     ```sh
     npm install -g ts-node
     ```

### 4. Set Up Virtual Environment

1. **Create a project directory**
   - Navigate to your desired location and create a new directory.
     ```sh
     mkdir my-typescript-project
     cd my-typescript-project
     ```

2. **Set local Node.js version**
   - Within the project directory, run the following command to specify the Node.js version:
     ```sh
     asdf local nodejs lts
     ```

### 5. Run TypeScript Code

1. **Create a TypeScript file**
   - Inside the project directory, create a file named `index.ts` and write the following sample code:
     ```typescript
     console.log("Hello, TypeScript!");
     ```

2. **Run TypeScript code**
   - In Terminal, run the following command to execute the TypeScript file:
     ```sh
     npx ts-node index.ts
     ```

With this setup, you are now ready to start developing with TypeScript on both Windows and macOS.
