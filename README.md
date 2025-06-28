# Ford WINCE AutoKit Project

This repository contains the necessary files to run CarPlay and Android Auto on Ford infotainment systems powered by the Windows CE (WINCE) operating system, using a Carlinkit CPC200-CCPM/CCPA USB dongle.

**Disclaimer:** These files modify the behavior of your car's infotainment system. Proceed with caution. Use at your own risk.

## Overview

The Ford SYNC system on some older models runs on Microsoft WINCE. This project leverages a scripting engine (`MortScript`) to launch the AutoKit software, which interfaces with a USB dongle to provide CarPlay and Android Auto functionality on the car's screen.

## Directory Structure

- **`/AutoKit`**: This is the main directory containing the core software for the CarPlay/Android Auto interface.
  - `BIN/`: Contains the primary executables (`AutoKit.exe`, `AutoKit-2.exe`), all required libraries (`.dll`), and configuration files.

- **`/LaunchAutoKit`**: Contains a launcher script (`Arthur.mscr`) and the `MortScript.exe` interpreter. This is used to start the main AutoKit application.

- **`/LaunchAutoKit-2`**: A secondary launcher, to start the `AutoKit-2.exe` variant from the `BIN` directory (alternative binary).

- **`/LaunchTotalCommander`**: A launcher script to start the Total Commander file manager. This is a utility for browsing the WINCE file system directly on the infotainment screen, useful for debugging and file manipulation.

- **`/TC`**: Contains the Total Commander application for WINCE (`cecmd.exe`), along with its language packs and plugins.

- **`/NaviMaps`**: Contains files the original navigation app by MapmyIndia. These files allow us to disguise the other directories as a map update to the infotainment system.

## Basic Usage

1.  Format a USB drive to FAT32.
2.  Copy the entire contents of this repository to the root of the USB drive (example - NaviMaps and other directories should be in the root of the USB drive).
4.  Insert the prepared USB drive into available USB port in the infotainment system.
5.  Go to Settings > General > Map Update > Yes (make sure the engine is running while contents are being copied).
6.  If anything goes wrong, you will have to manually copy the files from the USB drive to the infotainment system by opening the dashboard unit within the car that houses the infotainment system.
7.  Go to Settings > General > Map Path - Select \SDMEM\LaunchAutoKit\Arthur.exe to launch the Autokit application.
8.  Confirm the app works by connecting the Carlinkit CPC200-CCPM/CCPA dongle to the USB port in the infotainment system.