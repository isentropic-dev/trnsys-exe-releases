# TRNSYS Executable Releases

This repository contains the releases of a program that runs TRNSYS simulations.

## Installation Guide for Windows

### Step 1: Download the Installer

Go to the [Releases](https://github.com/isentropic-dev/trnsys-exe-releases/releases) page and download the latest `trnsys_{version}_x64-setup.exe` installer file.

### Step 2: Run the Installer

1. Double-click the downloaded `trnsys_{version}_x64-setup.exe` file.
2. Follow the on-screen instructions to complete the installation. The default installation directory is `C:\Users\{Your Username}\AppData\Local\trnsys`.

### Step 3: Configure Required Directories

After installation, you will need to define the locations of the TRNSYS directories in a configuration file. The program will read this file at runtime.

1. Create a JSON file at `C:\Users\{Your Username}\.config\trnsys\directories.json` with the following format:

   ```json
   {
       "root": "C:\\Path\\To\\TRNSYS\\Root",
       "exe": "C:\\Path\\To\\TRNSYS\\Executable",
       "resources": "C:\\Path\\To\\TRNSYS\\Resources",
       "userTypes": [
           "C:\\Path\\To\\User\\Type\\Directory",
           "C:\\Path\\To\\Another\\User\\Type\\Directory"
       ]
   }
   ```

2. Replace the example paths with the actual locations on your computer.  An example config for a hypothetical user named Angie would be:

   ```json
   {
       "root": "C:/Users/Angie/source/repos/isentropic-dev/trnsys-core/build/x64/Debug/dist",
       "exe": "C:/Users/Angie/source/repos/isentropic-dev/trnsys-core/build/x64/Debug/dist",
       "resources": "C:/Users/Angie/source/repos/isentropic-dev/trnsys-core/Resources",
       "userTypes": []
   }
   ```

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

### Step 3: Configure Required Directories

After installation, you will need to define the locations of the TRNSYS directories in a configuration file. The program will read this file at runtime.

1. Create a JSON file at `~/.config/trnsys/directories.json` with the following format:

   ```json
   {
       "root": "/Path/To/TRNSYS/Root",
       "exe": "/Path/To/TRNSYS/Executable",
       "resources": "/Path/To/TRNSYS/Resources",
       "userTypes": [
           "/Path/To/User/Type/Directory",
           "/Path/To/Another/User/Type/Directory"
       ]
   }
   ```

2. Replace the example paths with the actual locations on your computer.

## Automatic Updates

Once installed, this program will automatically update itself when newer versions are available. The directory paths specified in the `directories.json` configuration file should remain intact across updates.
