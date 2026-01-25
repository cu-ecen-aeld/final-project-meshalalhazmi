Low-Power Embedded Linux Digital Clock Using E-Paper Display

# Overview
This project implements a low power, appliance style embedded Linux system designed to function as a standalone digital clock with deterministic boot behavior and minimal runtime overhead. The system is built using Buildroot and deployed on a Raspberry Pi 5 platform.

The system initializes time from a dedicated hardware real-time clock (RTC) over I²C immediately at boot, renders the current time on a SPI-connected e-paper display, and subsequently performs network time synchronization (NTP) over Wi-Fi to correct any long term drifts

Display updates are rate limited to once per minute to reduce power consumption and extend e-paper panel longevity

# Motivation
The goal of this project is to build a complete low-power embedded Linux system that works as a standalone digital clock and can be expanded in the future into more complex applications. Even though the Raspberry Pi Foundation Raspberry Pi 5 is more powerful than what is needed for a clock, it is a common and well-supported platform that is often used in real embedded products

This project uses multiple communication methods, including I²C, SPI, and Wi-Fi networking, to gain hands-on experience with integrating different hardware interfaces under Linux. The design focuses on simplicity and reliability while creating a base system that could later be extended to support additional low-power, network-connected features

System Architecture
The system is designed as a single-purpose embedded device. Only the software and services needed for timekeeping, display output, and optional network synchronization are enabled.

High-level architecture:

I²C is used to read time from a hardware RTC

SPI and GPIO are used to control the e-paper display

Wi-Fi is used only for NTP time synchronization

The system continues to function correctly even if the network is unavailable

# Target Build System
Build System: Buildroot

# Hardware Platform
The hardware platform for this project is the Raspberry Pi 5. The system will be built using Buildroot and boot from a microSD card using the standard Raspberry Pi firmware and Linux kernel. All required peripherals, including SPI, I²C, GPIO, and Wi-Fi, are supported by the Linux kernel and Buildroot.

All hardware for this project will be sourced by myself, and no boards are requested to be borrowed from the department.

# Open Source Projects Used
This project does not use any additional open source projects.

# Previously Discussed Content
No previous assignment code (such as aesdsocket or aesdchar) is reused directly in this project. however, this project builds on content covered in previous assignments and lectures, including Buildroot configuration, Linux boot flow, root filesystem generation, kernel configuration, device tree usage, and user-space application development in C

# New Content
Content discussed in class but not implemented in previous assignments: 
- Integration of multiple hardware interfaces (SPI and I²C) in a single embedded system 
- Boot-time service sequencing for hardware initialization and networking 

Content not yet discussed in class: 
- E-paper display control and refresh management 
- Combining hardware RTC timekeeping with NTP synchronization 
- External system configuration using a user-editable boot partition

# Shared Material
This project does not leverage code or components from other coursework or from previous semesters

# Source Code Organization
TBD: Modify the content below:

Buildroot or Yocto Repository will be hosted at [TBD]

ApplicationX code will be hosted in in a repository at [TBD]

We request X additional repositories for application Y and Z.

# Group Overview
TBD: Fill in this section for group projects, delete it for individual projects

## Team project members:

TBD: list members.  List high level role in the project for each member

# Schedule Page
TBD: Include link to shared schedule wiki page below.