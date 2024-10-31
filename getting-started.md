---
title: Getting started
layout: home
nav_order: 2
---

# Getting started with ChoacuryOS

**GitHub repository link: [https://github.com/Pineconium/ChoacuryOS](https://github.com/Pineconium/ChoacuryOS)**

## Requirements
There are different requirements based on what platform you are on.

Base requirements to be able to run ChoacuryOS (Make sure your VM has these):

| Item         | Requirement |
| :----------- | :---------- |
| Base Memory  | 64 MB       |
| Video Memory | 9 MB        |
| Hard Disk    | 2 GB        |

### Windows
On Windows, you need to have WSL installed and find the folder on your Windows device, this can be done through the `/mnt/` folder on the WSL instance, this is where you will find all of the drives on your Windows computer.

If you are installing WSL, we recommend Ubuntu 24.04 LTS as we are sure that it works.

When you are sure that you have WSL set up, you can continue on to the [Linux part of this guide as it contains all of the information you will need](#linux-and-wsl).

### Linux (And WSL)
**We recommend Ubuntu 24.04 LTS as we are sure that it works**.

Make sure that you have the following items installed:
- NASM
- GCC
- GRUB Multiboot
- Makefile
- QEMU

{: .note }
The compiler uses the x86_64 version of QEMU. If you don't use that version of QEMU, replace `qemu-system-x86_64` in the compiler shell script with your version of QEMU.

### MacOS
We don't have an actual guide for MacOS (We've never built on it before), but instead, we recommend a Linux VM (Ubuntu 24.04 LTS) and then to follow the [Linux requirements](#linux-and-wsl).

### Other Operating Systems.
This will vary heavily from system-to-system, but you'll need to make sure your operating system has a version of GCC, NASM, Makefile, GRUB Multiboot, and (optionally) QEMU or any similar x86(-64) virtual machine software.

## Building
To build the latest version of ChoacuryOS, first download this repository.
Inside of your WSL instance, you need to navigate to where the route of the repository is on your Windows computer (`/mnt/`), make sure that the folder contains `compile.sh`, `compile_no_audio.sh` and `create-disk.sh`, if it does not and it contains folders such as `drivers`, you have gone too far, go up a level.

Make sure that you have the [correct requirements](#requirements) installed before continuing with this guide any futher, as without having the correct software installed, it will not work.

Inside of your WSL instance, it should now be in the correct directory, run `ls` to make sure that it contains all of the right scripts as mentioned above.

You can either run `sh compile.sh` or `sh compile_no_audio.sh`, you may need to append `sudo` to the beginning of the command for it to work however.
You should notice that it opens a QEMU window, you should be able to click inside of the QEMU window and then you will need to press return when GRUB pops up, as long as "Start Choacury" is selected.

You have now built and run the latest version of ChoacuryOS, type `help` to view all of the available commands.

To exit, press `CTRL+C` in the console or close the QEMU window (You may need to press CTRL+ALT+G to be able to do so).
## Development & Contribution
If you would like to help out, feel free to contribute to the project! (We have a Trello board but you will need to ask for access). You can also modify Choacury to your liking if you would to make your own OS! You may also join the [development server](https://discord.gg/qhgDWrzCvg) if you would like to.

We also have a Figma board that you may ask to access in the Discord server mentioned above.

You must:
- Make sure that the name of commits make sense and reflect the changes it contains
- Document your additions (We have a documentation repository) and add comments where needed

You must not:
- Remove any other code without asking first (Refactoring or cleaning up is okay).