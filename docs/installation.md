---
title: Installation
layout: default
nav_order: 2
---

# Installation Guide
{: .no_toc }

This guide will walk you through installing the z/TPF Visual Studio Code Debugger Extension.

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Prerequisites

Before installing the extension, ensure you have:

- **Visual Studio Code** version 1.105.1 or higher
- **Network access** to your z/TPF system
- **Valid credentials** for your Linux on IBM Z build environment

---

## Installation Methods

### Method 1: Install from the configured marketplace (Visual Studio Code / OpenVSX)

1. Open Visual Studio Code
2. Click on the **Extensions** icon in the Activity Bar (or press `Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Search for **"IBM z/TPF Debugger"** in the search bar
4. Click **Install** on the IBM z/TPF Debugger Extension
5. Reload Visual Studio Code when prompted

### Method 2: Install from VSIX File

If you have a `.vsix` file either from the [OpenVSX Registry](https://open-vsx.org/) or the z/TPF download page (https://www.ibm.com/support/pages/node/618267):

1. Open Visual Studio Code
2. Go to **Extensions** view (`Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Click the **"..."** menu at the top of the Extensions view
4. Select **"Install from VSIX..."**
5. Navigate to and select the `.vsix` file
6. Reload Visual Studio Code when prompted

---

## Verify Installation

After installation, verify the extension is active:

1. Open the **Extensions** view
2. Search for "IBM z/TPF Debugger" in the installed extensions
3. Clicking the extension will open the extension page in an editor
4. On the **Feature** tab in the opened editor, find the **Runtime Status** information.

---

## Updating the Extension

The extension will automatically check for updates from the configured marketplace (Visual Studio Code or Open VSX). 

Otherwise, you can manually update the extension by downloading a newer version of the `.vsix` file and installing using the instructions above.

---

## Uninstallation

To remove the extension:

1. Open the **Extensions** view
2. Find the z/TPF Debugger extension
3. Click the gear icon
4. Select **Uninstall**
5. Reload Visual Studio Code when prompted

---

## Next Steps

- [Getting Started Guide](getting-started.md) - Learn debugging basics
- [Features Overview](features.md) - Explore debugging capabilities