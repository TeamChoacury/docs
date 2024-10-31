---
title: Getting started
layout: home
---

# Getting started with ChoacuryOS

**GitHub repository link: https://github.com/Pineconium/ChoacuryOS**

## Requirements
There are different requirements based on what platform you are on.

Base requirements:
| Item         | Requirement |
| ------------ | ----------- |
| Base Memory  | 64 MB       |
| Video Memory | 9 MB        |
| Hard Disk    | 2 GB        |

### Windows
On Windows, you need to have WSL installed and find the folder on your Windows device, this can be done through the `/mnt/` folder on the WSL instance, this is where you will find all of the drives on your Windows computer.

If you are installing WSL, we recommend Ubuntu 24.04 LTS as we are sure that it works.

When you are sure that you have WSL set up, you can continue on to the [Linux part of this guide as it contains all of the information you will need](#linux-and-wsl).

### Linux (And WSL)
**We recommend Ubuntu 24.04 LTS as we are sure that it works**.

Make sure that you have the folling items installed:
- NASM
- GCC
- GRUB Multiboot
- Makefile
- QEMU

> [!NOTE]  
> The compiler uses the x86_64 version of QEMU. If you don't use that version of QEMU, replace qemu-system-x86_64 in the compiler shell script with your version of QEMU.

## Building
To build the latest version of ChoacuryOS, download this repository.
Inside of your WSL instance, you need to navigate to where the route of the repository is on your Windows computer (`/mnt/`), make sure that the folder contains `compile.sh`, `compile_no_audio.sh` and `create-disk.sh`, if it does not and it contains folders such as `drivers`, you have gone too far, go up a level.

Make sure that you have the [correct requirements](#requirements) installed before continuing with this guide any futher, as without having the correct software installed, it will not work.

## Development & Contribution