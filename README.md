# SPT (Single Player Tarkov) Setup Guide

Setup guide to getting SPT (Single Player Tarkov) **v4.1.3** and **Fika v2.4.2** running on your machine. 

## Prerequisites 

All required installers and runtimes can be found under [**Releases**](https://github.com/mikematos84/spt-setup-guide/releases).

### Runtimes

- **[DotNet Desktop Runtime](https://builds.dotnet.microsoft.com/dotnet/WindowsDesktop/10.0.11/windowsdesktop-runtime-10.0.11-win-x64.exe)** v10.0.11
- **[ASP.NET Core Runtime](https://builds.dotnet.microsoft.com/dotnet/aspnetcore/Runtime/10.0.11/aspnetcore-runtime-10.0.11-win-x64.exe)** v10.0.11

### Installers

- **[Battlestate Games Launcher](https://launcher.escapefromtarkov.com/launcher/download)** v15.0.0.4595
- **[SPT Installer](https://patcher.sp-tushonka.com/SPTInstaller.exe)** v4.1.3
- **[Fika Installer](https://github.com/project-fika/Fika-Installer/releases/download/v1.2.0/Fika-Installer.exe)** v2.4.2

> **Download files from the [Releases](https://github.com/mikematos84/spt-setup-guide/releases) page:**
> - **v1.0.0**: Download all 5 base setup files (runtimes + installers). Extract into a `downloads` folder before starting setup.
> - **v1.0.0-mods** (Optional): Quality-of-Life Mods Bundle - download for recommended mods (see Step 8).

## Steps

### Step 1: Install Runtimes
Install the [DotNet 10 Desktop Runtime](./downloads/windowsdesktop-runtime-10.0.11-win-x64.exe) and [ASP.NET 10 Core Runtime](./downloads/aspnetcore-runtime-10.0.11-win-x64.exe)

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

### Step 8: Installing Mods (Optional)

To add recommended mods, download mod files from the [v1.0.0-mods Release](https://github.com/mikematos84/spt-setup-guide/releases/tag/v1.0.0-mods):

**Option A: Direct Extract (Recommended)**
1. Right-click each mod file and select **Extract All**
1. In the extraction dialog, set the destination to: `C:\Games\SPT\`
1. Click **Extract** - the mod files will merge with existing directories (overwriting where necessary)

**Option B: Extract Then Copy**
1. Extract mod files to a temporary location (e.g., Desktop)
2. Open each extracted folder and copy all contents (BepInEx, SPT_Runtime, etc.)
3. Navigate to `C:\Games\SPT\` and paste - Windows will prompt to merge/overwrite, select **Yes**

**After Installation**
1. Restart your SPT server for mods to take effect
1. You can verify mods are loaded by checking the console output when the server starts

> **Note**: Only install mods that are compatible with SPT v4.1.3. Incompatible mods may cause crashes or unexpected behavior.

---

## 📋 Dependency Reference

This guide uses the following versions and sources. Use this section for troubleshooting or if you need to download files manually.

### Runtimes

| Component | Version | Download |
|-----------|---------|----------|
| **[DotNet Desktop Runtime](https://builds.dotnet.microsoft.com/dotnet/WindowsDesktop/10.0.11/windowsdesktop-runtime-10.0.11-win-x64.exe)** | 10.0.11 | [📥](https://builds.dotnet.microsoft.com/dotnet/WindowsDesktop/10.0.11/windowsdesktop-runtime-10.0.11-win-x64.exe) |
| **[ASP.NET Core Runtime](https://builds.dotnet.microsoft.com/dotnet/aspnetcore/Runtime/10.0.11/aspnetcore-runtime-10.0.11-win-x64.exe)** | 10.0.11 | [📥](https://builds.dotnet.microsoft.com/dotnet/aspnetcore/Runtime/10.0.11/aspnetcore-runtime-10.0.11-win-x64.exe) |

### Applications

| Component | Version | Official Guide | Download |
|-----------|---------|-----------------|----------|
| **[Battlestate Games Launcher](https://launcher.escapefromtarkov.com/launcher/download)** | 15.0.0.4595 | — | [📥](https://launcher.escapefromtarkov.com/launcher/download) |
| **[SPT (Single Player Tarkov)](https://patcher.sp-tushonka.com/SPTInstaller.exe)** | 4.1.3 | [SPT 4.x Installation Guide](https://wiki.sp-tushonka.com/en/SPT_4x/Installation_Guide) | [📥](https://patcher.sp-tushonka.com/SPTInstaller.exe) |
| **[Fika (Multiplayer Mod)](https://github.com/project-fika/Fika-Installer/releases/download/v1.2.0/Fika-Installer.exe)** | 2.4.2 | [Fika Installation Guide](https://wiki.project-fika.com/installing-fika/installation) | [📥](https://github.com/project-fika/Fika-Installer/releases/download/v1.2.0/Fika-Installer.exe) |

> **Note**: This guide is specifically tested with SPT v4.1.3 and Fika v2.4.2. If newer versions become available, refer to the official installation guides linked above for any changes to the setup process.

---

## 🎮 Recommended Mods

The following quality-of-life mods and utilities are included in the Release to enhance your SPT experience. See **Step 8: Installing Mods (Optional)** above for installation instructions.

### 🛠️ Utilities
Start with these tools to help manage your SPT installation and mods.

| Utility | Description | Version | File | Download |
|---------|-------------|---------|---|---|
| **[SPT Mod Manager](https://sp-mod.com/mod/2851/spt-mod-manager)** | Open-source mod manager for SPT featuring easy installation, management, and Forge integration | 0.5.3 | `SPT-Mod-Manager.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/SPT-Mod-Manager.zip) |

> **SPT Mod Manager Installation**: Extract the `SPT-Mod-Manager.zip` contents to `C:\Games\SPT\SPT_Mod_Manager` for easy access. Optionally create a desktop shortcut to the executable.

![SPT Mod Manager Interface](./assets/SPT-Mode-Manager.png)

### ⚠️ Required Mods
These mods are essential for proper server operation and have been tested for headless environments.

| Mod | Description | Version | File | Download |
|-----|-------------|---------|---|---|
| **[DynamicMaps](https://sp-mod.com/mod/1431/dynamic-maps)** | Interactive map markers, locations, and extract information | 1.2.1 | `DynamicMaps-1.2.1.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/DynamicMaps-1.2.1.zip) |
| **[UIFixes](https://sp-mod.com/mod/1342/ui-fixes)** | Fixes and improvements to the SPT UI | 6.0.1 | `Tyfon-UIFixes-6.0.1.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/Tyfon-UIFixes-6.0.1.zip) |
| **[Item Valuation](https://sp-mod.com/mod/2021/item-valuation)** | Displays item rarity coloring and marketplace pricing information. Temporary replacement until ODT-iteminfo is ported to SPT 4.1. | 2.1.0 | `acidphantasm-itemvaluation.7z` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/acidphantasm-itemvaluation.7z) |

### 🎮 Optional Quality-of-Life Mods

These mods improve gameplay experience, convenience, and information accessibility without significantly altering core mechanics.

> **⚠️ Testing Status**: These mods have **NOT been tested for headless operation**. Test locally at your own discretion; they may be promoted to Required once verified.

#### Search & Filter Tools

| Mod | Description | Version | File | Download |
|-----|-------------|---------|---|---|
| **[Task Search](https://sp-mod.com/mod/2909/task-search)** | Quick search functionality for tasks and objectives | 4.1 | `TaskSearch4.1.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/TaskSearch4.1.zip) |
| **[Trader Search](https://sp-mod.com/mod/2824/tradersearch)** | Filter trader stock live by item name with a search bar | 2.0.0 | `maschine-TraderSearch-2.0.0.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/maschine-TraderSearch-2.0.0.zip) |
| **[Linked Search In Stash](https://sp-mod.com/mod/2731/linkedsearchinstash)** | Search your stash for items compatible with selected equipment | 2.0.1 | `maschine-LinkedSearchInStash-2.0.1.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/maschine-LinkedSearchInStash-2.0.1.zip) |
| **[Weapon Builder Search](https://sp-mod.com/mod/2743/weaponbuildersearch)** | Live search functionality in the Weapon Builder and Modding screens | 2.0.0 | `maschine-WeaponBuilderSearch-2.0.0.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/maschine-WeaponBuilderSearch-2.0.0.zip) |

#### Information & Display

| Mod | Description | Version | File | Download |
|-----|-------------|---------|---|---|
| **[Compatibility Highlighter](https://sp-mod.com/mod/2859/compatibility-highlighter)** | Shows item compatibility and equipment compatibility info | 1.2.1 | `CompatibilityHighlighterV1.2.1.7z` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/CompatibilityHighlighterV1.2.1.7z) |
| **[Task Item Indicator](https://sp-mod.com/mod/2888/task-item-indicator)** | Visually highlights items needed for active tasks | 1.0.0 | `TaskItemIndicator_1.0.0.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/TaskItemIndicator_1.0.0.zip) |

#### Inventory & Trading

| Mod | Description | Version | File | Download |
|-----|-------------|---------|---|---|
| **[Merge Consumables](https://sp-mod.com/mod/1657/mergeconsumables)** | Groups similar consumable items together for inventory organization | 1.0 | `MergeConsumables.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/MergeConsumables.zip) |
| **[Use Loose Loot](https://sp-mod.com/mod/933/use-loose-loot)** | Allows using loose loot without picking it up | 1.6.0 | `Gaylatea-UseLooseLoot-1.6.0.7z` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/Gaylatea-UseLooseLoot-1.6.0.7z) |
| **[Fast Sell In Flea](https://sp-mod.com/mod/2207/fast-sell-in-flea)** | Quickly add items on the flea market with automatic fitting of the current price | 1.3.1 | `Kat-FastSellInFlea-1.3.1.7z` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/Kat-FastSellInFlea-1.3.1.7z) |

#### Gameplay Improvements

| Mod | Description | Version | File | Download |
|-----|-------------|---------|---|---|
| **[Climbable Ladders](https://sp-mod.com/mod/2649/climbable-ladders)** | Makes ladders climbable for improved map navigation | 1.0.4 | `tarkin-ladders-v1.0.4.zip` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/tarkin-ladders-v1.0.4.zip) |
| **[Simple Workout QTE](https://sp-mod.com/mod/1437/simple-workout-qte)** | Simplifies workout quick-time events for ease of use | 1.0 | `acidphantasm-simpleworkoutqte.7z` | [📥](https://github.com/mikematos84/spt-setup-guide/releases/download/v1.0.0-mods/acidphantasm-simpleworkoutqte.7z) |
