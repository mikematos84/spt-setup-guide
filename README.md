# SPT (Single Player Tarkov) Setup Guide

Setup guide to getting SPT (Single Player Tarkov) **v4.1.3** and **Fika v2.4.2** running on your machine. 

## Prerequisites 

All required installers and runtimes are available in the [**Latest Release**](https://github.com/mikematos84/spt-setup-guide/releases/latest).

### Runtimes

- DotNet 10 Desktop Runtime v10.0.11
- ASP.NET 10 Core Runtime v10.0.11

### Installers

- Battlestate Games Launcher v15.0.0.4595
- SPT Installer v4.1.3
- Fika Installer v2.4.2

> **Download all files from the [Releases](https://github.com/mikematos84/spt-setup-guide/releases) page** - Click "Latest Release" and download all 5 files. Extract them into a `downloads` folder on your machine before starting the setup process.

## Steps

### Step 1: Install Runtimes
If not already installed, install the [DotNet 10 Desktop Runtime](./downloads/windowsdesktop-runtime-10.0.11-win-x64.exe) and [ASP.NET 10 Core Runtime](./downloads/aspnetcore-runtime-10.0.11-win-x64.exe)

### Step 2: Install Battlestate Games Launcher
Launch the **Battlestate Games Launcher** and follow the installation prompts leaving all the **default settings**. 
> The default installation path should be `C:\Battlestate Games\BsgLauncher`

### Step 3: Install Escape from Tarkov
Launch the **Battlestate Game Launcher**, login, and install Escape From Tarkov. 
> Default installation path should be `C:\Battlestate Games\Escape from Tarkov`

### Step 4: Install SPT
Create a `C:\Games\SPT` directory and **copy** the **SPTInstaller.exe** from the **downloads** folder into that directory. Then, launch the **SPTInstaller.exe** from that directory, stepping through the prompts and leaving all the **default settings**


### Step 5: SPT (Pre-Fika) Setup

The following are steps you have to take in order to be ready to install Fika. It relies on files that are created by SPT when you run the server and play a game. 

1. Click **SPT.Server** and wait for it to say **Server has started, happy playing**
1. Click **SPT.Launcher** 
1. Click on the **Local Server** tile to connect to it. 
1. Click the **CREATE NEW PROFILE** button to create a profile.
   - Edition: Any one is fine
   - Name: `Test_SPT_User`
1. Click the `Test_SPT_User` Profile 
1. Click **START GAME** at the top right corner
1. Click **NEXT** on the character selection screen (you can simply pick any character and proceed)
1. Play a raid or Scav run to completion (whether you survive or die, the necessary files will be created)
1. Exit the game
1. Exit the launcher
1. Exit the terminal window for **SPT.Server** to shutdown the server

### Step 6: Install Fika 

1. **Copy** the **Fika-Installer.exe** to the `C:\Games\SPT` directory
1. Launch the **Fika-Installer.exe**
1. Enter 1 for **[1] Install Fika**
1. Once its been installed, **Press any key to continue**
1. Exit the terminal window to close the Fika Installer

### Step 7: Restoring Profiles
1. Copy your previously downloaded profile to `C:\Games\SPT\SPT_Runtime\user\profiles`
1. Click **SPT.Server** to launch the local server again
   > You will see some information regard profile migration. This is normal.
1. Click **SPT.Launcher** 
1. Click on the **Local Server** tile to connect to it
1. You should now see your old profile as an option on the screen. 
1. Click the tile for your restore profile
1. Click **START GAME** and you should see your restore profile in-game

---

## 📋 Dependency Reference

This guide uses the following versions and sources. Use this section for troubleshooting or if you need to download files manually.

### Runtimes

| Component | Version | Download |
|-----------|---------|----------|
| **DotNet Desktop Runtime** | 10.0.11 | [https://builds.dotnet.microsoft.com/dotnet/WindowsDesktop/10.0.11/windowsdesktop-runtime-10.0.11-win-x64.exe](https://builds.dotnet.microsoft.com/dotnet/WindowsDesktop/10.0.11/windowsdesktop-runtime-10.0.11-win-x64.exe) |
| **ASP.NET Core Runtime** | 10.0.11 | [https://builds.dotnet.microsoft.com/dotnet/aspnetcore/Runtime/10.0.11/aspnetcore-runtime-10.0.11-win-x64.exe](https://builds.dotnet.microsoft.com/dotnet/aspnetcore/Runtime/10.0.11/aspnetcore-runtime-10.0.11-win-x64.exe) |

### Applications

| Component | Version | Download | Official Guide |
|-----------|---------|----------|-----------------|
| **Battlestate Games Launcher** | 15.0.0.4595 | [https://launcher.escapefromtarkov.com/launcher/download](https://launcher.escapefromtarkov.com/launcher/download) | — |
| **SPT (Single Player Tarkov)** | 4.1.3 | [https://patcher.sp-tushonka.com/SPTInstaller.exe](https://patcher.sp-tushonka.com/SPTInstaller.exe) | [SPT 4.x Installation Guide](https://wiki.sp-tushonka.com/en/SPT_4x/Installation_Guide) |
| **Fika (Multiplayer Mod)** | 2.4.2 | [https://github.com/project-fika/Fika-Installer/releases/download/v1.2.0/Fika-Installer.exe](https://github.com/project-fika/Fika-Installer/releases/download/v1.2.0/Fika-Installer.exe) | [Fika Installation Guide](https://wiki.project-fika.com/installing-fika/installation) |

> **Note**: This guide is specifically tested with SPT v4.1.3 and Fika v2.4.2. If newer versions become available, refer to the official installation guides linked above for any changes to the setup process.