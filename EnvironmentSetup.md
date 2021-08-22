# Environment Setup

This guide is for new users who need to set up their environment.

- Windows Users
  - [WSL2](#Install-WSL2)
    - [WSL2 Troubleshooting](#WSL-2-Install-Errors)
  - [Terminal Manager](#Terminal-Manager)
  - [MobaXTerm](#Install-MobaXTerm)
- Mac & Linux Users
  - Use terminal already installed on your system
  - Let me (the instructor) or your ta's know if this needs updating
- [Chromebook Users](#Chromebook-Users)
- [Text Editors](#Text-Editors)

## Setup for Windows Users

### Install WSL 2

- [Follow instructions on the Windows blog](https://docs.microsoft.com/en-us/windows/wsl/install-win10#manual-installation-steps)
- Common pitfalls:
  - Windows is not fully up to date.
  - Did not reboot **before** running the change version command
  - Need to enable CPU virtualization in the BIOS. See the user manual for your computer.
- After installing Ubuntu from the Windows store, open Ubuntu once
- After the installion message finishes, you should be prompted to create a username and password.
  - Your username cannot have special characters or spaces or you will get a rules error

### Terminal Manager

In later labs, you will need two terminals open. It is absolutely alright to open multiple instances of Ubuntu, but it can be convenient to have a "tab" based setup. I recommend `Windows Terminal` (can be found in the Windows Store) or `MobaXTerm` (installation instructions below)

### Install MobaXTerm

[Download MobaXterm Home Edition: Installer Edition](https://download.mobatek.net/2062020111930940/MobaXterm_Installer_v20.6.zip)

- Extract the contents to your Desktop.
- Double-click to run the installer
- Once installed, run the program one time - this finishes the installation
- You can now delete the installation files
- Open Moba. You can now choose to run WSL Ubuntu _or_ Moba bash.
  - To change terminals, go to Settings -> Configuration. Select the Terminal tab. In the dropdown at the bottom, change from `bash` to `WSL Ubuntu`
- Keep your SSH session "alive"
  - `Settings` -> `Configuration`. In `SSH` tab, checkmark the box corresponding to `SSH keepalive`

If you **do not have administrative privileges** on the system, you will need to install MobaXTerm (step 3) and install Cygutils (instructions below) in order to perform the labs.

- In Moba, select the Packages icon at the top.
- Wait for the package menu to appear.
- In the search bar, type "cygutils". Select the package from the result listings
- Select Install / Update.
- Restart Moba. Start Local Terminal should work
- In the toolbar for Moba, go to Settings -> Configuration
- In the General tab, check the following two fields are populated with the following values:
  - Persistent home directory: `_MyDocuments_\MobaXterm\home`
  - Persistent root directory: `_MyDocuments_\MobaXterm\slash`

## Text Editors:

I recommend [Visual Studio Code](https://code.visualstudio.com/) as a cross platform solution (plus dark mode looks cool). You can also use any default text editor on your system (Notepad, Notepad++, or whatever Mac's have).

## Mac & Linux Users

- You should have a terminal already installed. Hunt it down ;)

## Chromebook Users

This guide here refers to a [Chrome Extension for SSH connections](https://www.lifewire.com/how-to-use-chromebook-ssh-client-4690108)

- To use your AWS Educate Private Key, you'll need to select "Import..." and browse to your  
  key file - you can then select your key from the dropdown.
- You may need to make a "failed" connection in order to get the permission to access files  
  questions to pop up.

## WSL 2 Install Errors

- Error message:

```
The requested operation could not be completed due to a virtual disk system limitation.
Virtual hard disk files must be uncompressed and unencrypted and must not be sparse.
```

- Follow [WSL2 VHD Issue Guide](https://utf9k.net/blog/wsl2-vhd-issue/)
