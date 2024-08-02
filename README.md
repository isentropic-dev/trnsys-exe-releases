# TRNSYS Executable Releases

This repository contains the releases of a program that runs TRNSYS simulations.

## Installation Guide for Windows

### Step 1: Download the Installer

Go to the [Releases](https://github.com/isentropic-dev/trnsys-exe-releases/releases) page and download the latest `trnsys_{version}_x64-setup.exe` installer file.

### Step 2: Run the Installer

1. Double-click the downloaded `trnsys_{version}_x64-setup.exe` file.
2. Follow the on-screen instructions to complete the installation. The default installation directory is `C:\Users\{Your Username}\AppData\Local\trnsys`.

### Step 3: Set Up Symlinks for Required Directories

After installation, you will need to create symbolic links (symlinks) for the `lib`, `resources`, and `userlib` directories to their corresponding TRNSYS library and resource files using PowerShell:

1. Open **PowerShell** with administrative privileges:
   - Press `Win + R`, type `powershell`, and press `Ctrl + Shift + Enter`.
2. Execute the following commands, replacing the example paths with the actual paths:

   ```powershell
   New-Item -ItemType SymbolicLink -Path "$env:LocalAppData\trnsys\lib" -Target "$env:UserProfile\source\repos\isentropic-dev\trnsys-core\build\x64\Debug\dist"
   New-Item -ItemType SymbolicLink -Path "$env:LocalAppData\trnsys\resources" -Target "$env:UserProfile\source\repos\isentropic-dev\trnsys-core\Resources"
   New-Item -ItemType SymbolicLink -Path "$env:LocalAppData\trnsys\userlib" -Target "C:\Path\To\User\Type\Libraries"
   ```

### Step 4: Verify the Symlinks

Navigate to the installation directory (default is `C:\Users\{Your Username}\AppData\Local\trnsys`) and verify that the `lib`, `resources`, and `userlib` directories correctly link to the respective TRNSYS directories.

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
   ```

2. Move the `trnsys.app` application to your preferred location, such as `/Applications`.

### Step 3: Create Symlinks for Required Directories

Inside the `trnsys.app` package, create symbolic links (symlinks) for the `lib`, `resources`, and `userlib` directories to their corresponding TRNSYS library files:

1. Open the **Terminal** application.
2. Navigate to the `Contents/MacOS` directory of the `trnsys.app` package:

   ```sh
   cd /Path/To/trnsys.app/Contents/MacOS
   ```

3. Run the following commands, replacing `/Path/To/TRNSYS/Libraries` with the actual path:

   ```sh
   ln -s "/Path/To/TRNSYS/lib" lib
   ln -s "/Path/To/TRNSYS/resources" resources
   ln -s "/Path/To/TRNSYS/userlib" userlib
   ```

### Step 4: Verify the Symlinks

Navigate to the `Contents/MacOS` directory of the `trnsys.app` package and ensure the `lib`, `resources`, and `userlib` directories correctly link to the respective TRNSYS directories.

## Automatic Updates

Once installed, this program will automatically update itself when newer versions are available. The symbolic links to the TRNSYS files created during setup should remain intact across updates.
