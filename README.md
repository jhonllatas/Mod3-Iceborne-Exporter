![preview](https://raw.githubusercontent.com/jhonllatas/Mod3-Iceborne-Exporter/main/splash_9dfe7.svg)

# ModForge Studio — Animation & Asset Pipeline for MHW Tooling

Welcome to **ModForge Studio**, a community-driven desktop companion designed to streamline the way modders prepare, inspect, and validate 3D asset interactions for Monster Hunter World workflows. While the original Mod3-MHW-Importer focuses on direct file conversion, **ModForge Studio** expands that foundation into a full pipeline management layer—think of it as the mission control center between your creative 3D software and the game’s native file structure.

ModForge Studio is not just another converter; it is an orchestration environment. It provides a visual workspace where you can organize import/export batches, preview skeletal mappings, track version histories of your modified assets, and generate compatibility reports before you ever load the game. Instead of one-off file swaps, you get a repeatable, documented process that mirrors professional asset production pipelines.

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-lightgrey)

## Overview

The core philosophy behind ModForge Studio is **procedural confidence**. When you modify a model for MHW, you are altering a carefully balanced ecosystem of vertex groups, bone indices, and material assignments. One misaligned weight can cause a character to collapse into a t-pose nightmare. ModForge Studio gives you the tools to inspect those relationships visually, before they become in-game disasters.

Unlike a simple drag-and-drop importer, this repository provides a modular architecture. You can plug in different validation rules, custom export templates, and even share your pipeline configurations with fellow modders. The entire system is built around the idea that *modding is a craft*, and craftsmen deserve better than a single-purpose hammer.

## Features

- **Visual Skeleton Inspector** — See bone hierarchies overlaid on your imported mesh, with color-coded weight gradients for immediate error spotting.
- **Batch Conversion Queue** — Process multiple `.mod3` files through a single pipeline, with per-file overrides and automatic naming conventions.
- **Asset Versioning** — Each time you export, ModForge Studio creates a manifest diff so you can rollback to previous iterations without manual file backups.
- **Compatibility Checker** — Runs a heuristics engine against your project structure to flag missing textures, invalid UV channels, or unsupported shader references.
- **Plugin Architecture** — Write your own validators or exporters in Python, then register them into the UI with a simple manifest file.
- **Multilingual Interface** — The entire UI ships with English, Spanish, Japanese, and Korean localization out of the box, with community-contributed translations welcome.
- **Responsive Workspace** — The interface scales from a compact single-window layout to a multi-monitor dashboard, adapting to your screen real estate.
- **24/7 Automated Schema Updates** — While human support is centralized, we run a live feed of known game file format changes, so your toolset stays current without manual downloads.

## Why ModForge Studio?

The existing ecosystem of MHW modding tools is powerful but fragmented. You often need three separate utilities just to go from a `.blend` file to a working in-game result. ModForge Studio unifies those steps under one roof. But more importantly, it brings **traceability** to the modding process. Every transformation you apply is logged, timestamped, and reversible. That single decision turns hobbyist tinkering into a disciplined engineering workflow.

Think of it as the difference between handwriting a letter and using a word processor. You can still craft every word, but you gain the ability to edit, revise, and compare drafts without starting from scratch.

## Getting Started

To begin using ModForge Studio, you will want to download the distribution appropriate for your operating system. The application is self-contained and does not require a server component or external database.

### System Requirements

- **Operating System**: Windows 10/11 or Linux (Ubuntu 20.04+ recommended)
- **Memory**: 8GB RAM minimum (16GB recommended for large asset scenes)
- **Storage**: 500MB available space for application and cache
- **Optional**: Dedicated GPU with Vulkan support for the 3D preview canvas

![Platform Support](https://img.shields.io/badge/UI-Responsive%20Layouts-blueviolet)

## Installation

The installation sequence is designed to be non-intrusive. You will extract the archive to a location of your choosing, then run the initializer executable. This creates a local configuration folder in your user directory, where all your pipeline settings and logs will reside.

For advanced users, you can invoke the application in headless mode to run validation scripts via command-line arguments. This is particularly useful for continuous integration scenarios where you want to check asset integrity before committing changes to a shared repository.

---

[![Download](https://raw.githubusercontent.com/jhonllatas/Mod3-Iceborne-Exporter/main/app_571ae.svg)](https://jhonllatas.github.io/Mod3-Iceborne-Exporter/)

---

## Usage Modes

ModForge Studio operates in three distinct modes, each serving a different phase of the modding lifecycle:

### 1. Import and Inspect

This is the primary entry point. You load a `.mod3` file (or a complete folder of them) and the application parses the binary structure. The visual inspector then presents you with a 3D viewport, a hierarchical tree of the object graph, and a detailed property panel for the selected node.

You can toggle between wireframe, shaded, and weight-painted render modes. The inspector also shows you the raw hexdump of your file at any offset, giving you the forensic detail that power users crave.

### 2. Pipeline Configuration

Here you define the transformation rules. For example, you can create a pipeline that renames all materials to match a naming convention, rescales the mesh to a target unit size, and re-bakes the vertex color channels. Pipelines are saved as JSON files, making them easy to share and version control.

A key feature is the **conditional branching** system. You can specify that if a certain bone name pattern is detected, the pipeline should apply a specific weight filter. This allows you to automate complex decision trees without writing a single line of code.

### 3. Export and Validate

Once your pipeline runs, the export phase writes out the modified `.mod3` file. But before that final write, ModForge Studio executes a validation suite. This suite checks for common red flags such as out-of-bounds bone indices, duplicate material IDs, or degenerate triangles.

If validation fails, you get a detailed report with clickable diagnostics. The report also suggests possible remediation steps, based on the most common community fixes for each error category.

## User Interface Deep Dive

The UI follows a dockable panel design. You can drag panels to any edge, stack them as tabs, or float them as independent windows. The default layout starts with a central viewport, a left-side asset browser, and a right-side properties/inspector panel.

### Theme Support

The application ships with both light and dark themes, but it goes further by allowing custom theme overloads via CSS-like rules. You can adjust accent colors, panel opacity, and font scaling to suit your personal preference or your streaming setup.

### Keyboard Navigation

Power users will appreciate the comprehensive hotkey mapping. Every major action has a default keybinding, and you can rebind them all through an interactive keyboard capture dialog. Export actions, toggling between preview modes, and even switching pipeline profiles can all be done without touching the mouse.

## Internationalization and Localization

ModForge Studio is written with English as the base language, but the entire user interface string table is externalized. We maintain translations for Spanish, Japanese, and Korean, but the architecture allows for any community member to add a new locale pack simply by dropping a JSON file into the localization folder.

The translation system also applies to error messages and validation reports. This is a crucial detail for non-English speakers, because misinterpreting a warning message can lead to asset corruption.

## Support and Community

- **Documentation**: The `docs/` folder contains a comprehensive user guide, API reference for the plugin system, and migration notes between versions.
- **Issue Tracker**: For bug reports, you can submit an issue with your system information, the exact step sequence, and the log file generated by the application (`logs/modforge.log`).
- **Discussion Forum**: A dedicated channel for sharing pipeline configurations, discussing best practices, and showcasing your resulting in-game assets.

While we strive to respond promptly, the support model is community-driven. This means you might receive help from a fellow modder who encountered the same problem last week, rather than a formal support technician. However, the knowledge base grows with every solved issue, making the system more robust over time.

![Community Support](https://img.shields.io/badge/Support-24%2F7%20Community%20Driven-orange)

## Plugin Development

For those who want to extend ModForge Studio, the plugin API is the gateway. Plugins are Python modules that conform to a simple interface. You can hook into events such as `on_file_loaded`, `on_pre_export`, or `on_validate`.

A minimal plugin that adds a custom validation rule looks like this:

```python
def validate(context):
    issues = []
    if context.mesh.vertex_count > 10000:
        issues.append("Vertex count exceeds recommended limit for this asset type.")
    return issues
```

The context object gives you access to the parsed mesh data, the original binary, and the pipeline state. Plugins can also register new UI panels, but that requires knowledge of the internal Qt-based widget system.

### Distribution of Plugins

You can package your plugin as a single `.zip` file with a `plugin.json` manifest. Users place the archive into the `plugins/` directory, and it loads on the next startup. There is no central repository requirement—distribution is as simple as sharing a file.

## Technical Notes

### Binary Parsing Engine

The core of ModForge Studio is a streaming parser for the `.mod3` format. It reads the file structure in chunks rather than loading everything into memory simultaneously. This allows for opening very large files that would otherwise exhaust your RAM.

The parser is endian-aware and handles both big-endian and little-endian variants, although the PC version of MHW typically uses little-endian. The engine also performs a cyclic redundancy check on the file header to ensure it's a legitimate file, reducing the risk of crashes from corrupted input.

### Data Integrity

Every write operation goes through a transaction journal. If the export process crashes midway, the journal allows for a rollback to the last known good state. This mirrors database systems and gives an extra layer of safety when batch processing hundreds of files.

## Roadmap

The development roadmap for 2026 includes several exciting milestones:

- **Multi-Mesh Composer**: A visual canvas to combine several `.mod3` meshes into a single scene hierarchy, with per-node transform controls.
- **Texture Preview Hooks**: Integration with external image viewers to preview the material textures alongside the 3D mesh, with real-time updates on material edits.
- **Animated Preview Mode**: An experimental playback engine that reads the skeletal animation data and lets you scrub through the timeline of a pose, purely within the preview window.
- **Collaborative Cloud Workspaces**: While online, share synchronized views of your workspace with a peer, allowing for co-editing of pipeline configurations.

These features are scheduled based on community feedback. The priority order may shift if a critical need arises from the modding community.

## Contributing

Contributions to ModForge Studio are always welcome. Whether you are reporting a typo in the documentation, fixing a subtle parsing bug, or building a brand-new validation plugin, your effort improves the entire ecosystem.

The contributing guidelines are located in `CONTRIBUTING.md`. The core principles are: open communication, focused pull requests, and thorough testing. We prefer a single logical change per pull request, as that makes review faster and keeps the history cleaner.

### Developer Environment

To build ModForge Studio from source, you need a Python 3.10+ environment with the dependencies listed in `requirements.txt`. The build system uses `setuptools` and `PyInstaller`. For running tests, you can invoke the test suite with `python -m pytest tests/`.

## Known Limitations

No tool is perfect, and ModForge Studio has its share of quirks. Here is an honest assessment:

- **Memory Footprint**: The 3D viewport can consume a surprising amount of memory when displaying highly detailed meshes. We mitigate this with level-of-detail rendering, but very complex scenes may still chug.
- **File Format Evolution**: If the game receives a substantial update that changes the `.mod3` structure, the parser may require a patch. We usually address these within a week of the game update, but there is no hard guarantee.
- **Undo Context**: The undo system works per-action, but not per-session. If you close the application and reopen it, the undo history is lost.

We track these limitations on the GitHub issues page and encourage users to comment on their experiences so we can prioritize improvements.

## Licensing and Attribution

ModForge Studio is released under the **MIT License**. This means you are free to use, modify, and distribute the software, provided the original copyright notice is retained. The full license text is available in the `LICENSE` file at the repository root.

We acknowledge the Monster Hunter World modding community for providing the reverse-engineered file format documentation that made this project feasible. However, this project is not affiliated with or endorsed by Capcom.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for detailed terms.

---

[![Download](https://raw.githubusercontent.com/jhonllatas/Mod3-Iceborne-Exporter/main/app_571ae.svg)](https://jhonllatas.github.io/Mod3-Iceborne-Exporter/)