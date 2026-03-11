---
title: Installation
layout: default
nav_order: 2
---

# Installation Guide

This guide will walk you through installing the z/TPF VS Code Debugger Extension.

{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Prerequisites

Before installing the extension, ensure you have:

- **Visual Studio Code** version 1.75.0 or higher
- **Network access** to your z/TPF system
- **Valid credentials** for z/TPF system access

---

## Installation Methods

### Method 1: Install from VS Code Marketplace (Recommended)

1. Open Visual Studio Code
2. Click on the **Extensions** icon in the Activity Bar (or press `Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Search for **"z/TPF Debugger"** in the search bar
4. Click **Install** on the z/TPF Debugger Extension
5. Reload VS Code when prompted

### Method 2: Install from VSIX File

If you have a `.vsix` file:

1. Open Visual Studio Code
2. Go to **Extensions** view (`Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Click the **"..."** menu at the top of the Extensions view
4. Select **"Install from VSIX..."**
5. Navigate to and select the `.vsix` file
6. Reload VS Code when prompted

### Method 3: Install via Command Line

```bash
code --install-extension IBM.ztpf-debugger
```

---

## Verify Installation

After installation, verify the extension is active:

1. Open the **Extensions** view
2. Search for "z/TPF Debugger" in the installed extensions
3. You should see the extension listed with a green checkmark

---

## Initial Configuration

After installation, configure your debug connection:

1. Create a `.vscode` folder in your project (if it doesn't exist)
2. Create a `launch.json` file with your debug configuration
3. Configure your z/TPF system connection details

Example `launch.json`:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug z/TPF",
      "type": "ztpf",
      "request": "launch",
      "program": "${file}",
      "stopOnEntry": false
    }
  ]
}
```

---

## Troubleshooting

### Extension Not Loading

If the extension doesn't load:

1. Check the **Output** panel (`View > Output`)
2. Select **"z/TPF Debugger"** from the dropdown
3. Review any error messages
4. Ensure VS Code is up to date

### Connection Issues

If you can't connect to your z/TPF system:

1. Verify network connectivity
2. Check firewall settings
3. Confirm credentials are correct
4. Review debug configuration

### Getting Help

If you encounter issues:

- Check the [GitHub Issues](https://github.com/IBM/ztpf-debugger/issues) page
- Review existing issues or create a new one
- Include VS Code version, extension version, and error logs

---

## Updating the Extension

The extension will automatically check for updates. To manually update:

1. Open the **Extensions** view
2. Find the z/TPF Debugger extension
3. Click **Update** if available
4. Reload VS Code when prompted

---

## Uninstallation

To remove the extension:

1. Open the **Extensions** view
2. Find the z/TPF Debugger extension
3. Click the gear icon
4. Select **Uninstall**
5. Reload VS Code when prompted

---

## Next Steps

- [Getting Started Guide](getting-started.md) - Learn debugging basics
- [Features Overview](features.md) - Explore debugging capabilities