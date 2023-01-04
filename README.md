# Workspace for Espressif's SoC development on Zephyr

This simple repository provides Visual Studio Code (aka VSCode) necessary
configurations for [Espressif](https://www.espressif.com/) SoC development on [Zephyr](https://github.com/zephyrproject-rtos/zephyr)

* Configuration of VSCode workspace
* Debug Launch for ESP32, ESP32S2/S3 and ESP32C3
* OpenOCD ESP config files
* ESP32/S2/S3/C3 SVD files needed for debugger

**Note:** Currently S3 is not yet supported on Zephyr. It will be soon!

## Getting started
Follow this simple steps to simplify your Zephyr development in VSCode:

1. Follow Zephyr's latest [Getting Started Guide](https://docs.zephyrproject.org/latest/getting_started/index.html)
2. Switch to yout `zephyrproject` path from terminal:
> cd <some_path>/zephyrproject
3. Clone this repository in your `zephyrproject`:
> git clone https://github.com/LucasTambor/EspZephyrWS.git
4. Open [EspZephyr.code-workspace](https://github.com/LucasTambor/EspZephyrWS/blob/main/Espressif_Zephyr.code-workspace) as a workspace in VSCode:
> File -> Open Workspace...
(be careful: last opened active workspace must be closed)

**Note:** This repository must be placed in your `zephyrproject` folder!

## Workspace Configuration
The [EspZephyr.code-workspace](https://github.com/LucasTambor/EspZephyrWS/blob/main/Espressif_Zephyr.code-workspace)
contains all neccessary workspace configuration accepted by Zephyr project like:
* Folders to open (like `zephyrproject`)
* Minimal code styling settings (TABs/SPACES)
* Exclude paths (needed to reduce CPU usage while workspace is opened)

## OpenOCD for ESP32

The Open On-Chip Debugger (OpenOCD) is an open source application that implements a remote GDB server for a wide variety of embedded devices.
The ESP32 modules need some patches that are not available in the upstream project.
For this reason Espressif maintains its own version of the repository.

The custom OpenOCD can be obtained at [OpenOCD ESP32](https://github.com/espressif/openocd-esp32/releases).

Download the latest version and extract it at your preferred location.
Overwrite the `openocd_root` configuration at [EspZephyr.code-workspace](https://github.com/LucasTambor/EspZephyrWS/blob/main/Espressif_Zephyr.code-workspace) with the path where you extract it.

## Debug

To launch the project you need [Cortex-Debug](https://marketplace.visualstudio.com/items?itemName=marus25.cortex-debug)
extension for Visual Studio Code. Please install it and follow it's installation guide.

After installing `Cortex-Debug` and `OpenOCD` on your system, the debug button
should appear in your VSCode GUI.

The [.vscode/launch.json](https://github.com/Nukersson/zephyr_vscode_workspace/blob/master/.vscode/launch.json)
describes launch configuration for `Cortex-Debug`.

# Acknowledges

Inspired by https://github.com/Nukersson/zephyr_vscode_workspace
