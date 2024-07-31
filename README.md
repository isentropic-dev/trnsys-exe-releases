# TRNSYS Executable Releases

This repository contains the releases of a program that runs TRNSYS simulations.

## Installation Guide for Windows

### Step 1: Download the Installer

Go to the [Releases](https://github.com/isentropic-dev/trnsys-exe-releases/releases) page and download the latest `trnsys_{version}_x64-setup.exe` installer file.

### Step 2: Run the Installer

1. Double-click the downloaded `trnsys_{version}_x64-setup.exe` file.
2. Follow the on-screen instructions to complete the installation. The default installation directory is `C:\Users\{Your Username}\AppData\Local\trnsys`.

### Step 3: Create a Symlink to the TRNSYS Library

After installation, create a symbolic link (symlink) to the directory containing the TRNSYS library and resource files using PowerShell:

1. Open **PowerShell** with administrative privileges:
   - Press `Win + R`, type `powershell`, and press `Ctrl + Shift + Enter`.
2. Execute the following command, replacing `C:\Path\To\Directory\Containing\TRNSYS\Files` with the actual path:

   ```powershell
   New-Item -ItemType SymbolicLink -Path "$env:LocalAppData\trnsys\lib" -Target "C:\Path\To\Directory\Containing\TRNSYS\Files"
   ````

### Step 4: Verify the Symlink

Navigate to the installation directory (default is `C:\Users\{Your Username}\AppData\Local\trnsys`) and verify that the `lib` directory correctly links to the TRNSYS directory.

## Installation Guide for Mac

**Note**: Only Mac computers with Apple silicon (M1, M2, and M3) are supported.

### Step 1: Download the Installer

Go to the [Releases](https://github.com/isentropic-dev/trnsys-exe-releases/releases) page and download the latest `trnsys_aarch64.app.tar.gz` file.

### Step 2: Expand the Archive

1. Expand the downloaded `trnsys_aarch64.app.tar.gz` file by either:
   - Double-clicking the file, or
   - Using the following terminal command:

   ```sh
   tar -xzvf trnsys_aarch64.app.tar.gz
   ````

2. Move the `trnsys.app` application to your preferred location, such as `/Applications`.

### Step 3: Create a Symlink to the TRNSYS Library

Inside the `trnsys.app` package, create a symbolic link (symlink) to the directory containing the TRNSYS library files:

1. Open the **Terminal** application.
2. Navigate to the `Contents/MacOS` directory of the `trnsys.app` package:

   ```sh
   cd /Path/To/trnsys.app/Contents/MacOS
   ````

3. Run the following command, replacing `/Path/To/Directory/Containing/TRNSYS/Files` with the actual path:

   ```sh
   ln -s "/Path/To/Directory/Containing/TRNSYS/Files" lib
   ````

### Step 4: Verify the Symlink

Navigate to the `Contents/MacOS` directory of the `trnsys.app` package and ensure the `lib` directory correctly links to the TRNSYS directory.

## Automatic Updates

Once installed, this program will automatically update itself when newer versions are available. The symbolic link to the TRNSYS files created during setup should remain intact across updates.
