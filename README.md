# ubuntu_in_cmd-
Unfortunately, installing `w3m` directly from a batch file in Windows isn't feasible because `w3m` is primarily designed for Unix-like systems and doesn't have a native Windows version. However, you can use a workaround to run `w3m` in Windows, such as through Cygwin or Windows Subsystem for Linux (WSL). Here's how you can do it using WSL:

1. **Enable WSL**:
   - Open PowerShell as Administrator.
   - Run the following command:
     ```
     dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
     ```
   - Restart your computer when prompted.

2. **Install a Linux distribution from Microsoft Store**:
   - Open Microsoft Store.
   - Search for "Linux" and choose a distribution such as Ubuntu.
   - Install the distribution.

3. **Initialize and set up the Linux distribution**:
   - Launch the installed Linux distribution from the Start menu.
   - Follow the on-screen instructions to complete the setup, including creating a user account and password.

4. **Install `w3m` within the Linux distribution**:
   - Once you're inside the Linux distribution's terminal, you can install `w3m` using the package manager. For example, for Ubuntu, you would run:
     ```
     sudo apt update
     sudo apt install w3m
     ```

5. **Create a batch file to run WSL with `w3m`**:
   - Open Notepad or any text editor.
   - Enter the following command:
     ```
     wsl w3m %1
     ```
   - Save the file with a `.bat` extension, such as `run_w3m.bat`.

6. **Run `w3m` from the batch file**:
   - Double-click on `run_w3m.bat`.
   - It will prompt you to enter a URL. Once you enter a URL, it will open in `w3m` within the WSL environment.

This setup allows you to use `w3m` within Windows via WSL. Note that this solution requires Windows 10 or later with WSL enabled. Additionally, performance may vary compared to running `w3m` natively on a Unix-like system.


Setting up the Windows Subsystem for Linux (WSL) and installing a Linux distribution from the command prompt (CMD) is a bit more complex but can be achieved with a series of commands. Here's a step-by-step guide:

1. **Open Command Prompt as Administrator**:
   - Press `Win + X` and choose "Command Prompt (Admin)" or search for "cmd" in the Start menu, right-click on "Command Prompt," and select "Run as administrator."

2. **Enable WSL**:
   - Run the following command:
     ```
     dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
     ```

3. **Install a Linux distribution**:
   - To install a specific Linux distribution from the Microsoft Store, you can use the `wsl --install` command. However, this command is only available in Windows 10 version 1903 and later. If you're using an older version, you need to manually install a distribution from the Microsoft Store.
   - For example, to install Ubuntu, you can use the following command:
     ```
     wsl --install -d Ubuntu
     ```
   - This command will automatically download and install Ubuntu from the Microsoft Store.

4. **Initialize the installed Linux distribution**:
   - After the installation is complete, you need to initialize the distribution. You can do this using the `wsl --set-version` command.
   - For example, to set Ubuntu to version 2 (WSL 2), run the following command:
     ```
     wsl --set-version Ubuntu 2
     ```

5. **Set up the Linux distribution**:
   - Launch the installed Linux distribution from the Start menu or by running its executable from the command prompt.
   - Follow the on-screen instructions to complete the setup, including creating a user account and password.

6. **Install `w3m` within the Linux distribution**:
   - Once you're inside the Linux distribution's terminal, you can install `w3m` using the package manager. For example, for Ubuntu, you would run:
     ```
     sudo apt update
     sudo apt install w3m
     ```

7. **Create a batch file to run WSL with `w3m`**:
   - Open Notepad or any text editor.
   - Enter the following command:
     ```
     wsl w3m %1
     ```
   - Save the file with a `.bat` extension, such as `run_w3m.bat`.

8. **Run `w3m` from the batch file**:
   - Double-click on `run_w3m.bat`.
   - It will prompt you to enter a URL. Once you enter a URL, it will open in `w3m` within the WSL environment.

That's it! You've now set up `w3m` within Windows using the Windows Subsystem for Linux (WSL) entirely from the command prompt. You can now use `w3m` to browse the web from the command line.
