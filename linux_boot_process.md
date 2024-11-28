# Linux Boot Process (Modern Systems)

## Overview
The Linux boot process has evolved with modern systems, incorporating technologies like systemd and UEFI. This document explains the step-by-step process of booting a modern Linux system.

## Stages of Linux Boot Process

### 1. UEFI/BIOS Initialization
- When the computer is powered on, the firmware (UEFI or traditional BIOS) performs POST (Power-On Self-Test)
- Checks hardware components and initializes basic system configuration
- Locates and loads the bootloader from the designated boot device

### 2. Bootloader (GRUB 2)
- GRUB 2 (Grand Unified Bootloader) takes control
- Presents boot menu to select operating system or kernel
- Loads the selected Linux kernel and initial RAM disk (initrd/initramfs)
- Passes kernel parameters and configuration

### 3. Kernel Initialization
- Kernel decompresses itself into memory
- Sets up essential system functions
- Mounts the root filesystem
- Initializes hardware drivers
- Prepares to hand control to the init system

### 4. Systemd Initialization
- Systemd becomes the first process (PID 1)
- Responsible for bringing up the entire system
- Manages system services, mounts, and system state
- Reads configuration from `/etc/systemd`
- Starts parallel service initialization

### 5. User Space Startup
- Starts essential system services
- Configures network interfaces
- Launches graphical environment (if configured)
- Prepares login prompts or display manager

![Screenshot from 2024-11-28 14-00-01](https://github.com/user-attachments/assets/dbd75988-783f-4da6-8c67-64883f25cb76)
