---
title: Getting Started
layout: default
nav_order: 3
---
# Getting Started with z/TPF Debugger

This guide will help you get up and running with the z/TPF VS Code Debugger Extension.

{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Quick Start

### Step 1: Install the Extension

Install the extension from the VS Code Marketplace. See the [Installation Guide](installation.md) for detailed instructions.

### Step 2: Configure Debug Connection

1. Open your z/TPF project in VS Code
2. Create a debug configuration (`.vscode/launch.json`)
3. Configure your z/TPF system connection details

### Step 3: Start Debugging

1. Open a z/TPF source file
2. Set breakpoints by clicking in the gutter
3. Press `F5` to start debugging

---

## Basic Debugging Workflow

### 1. Set Breakpoints

Click in the gutter (left of line numbers) to set breakpoints where you want execution to pause.

### 2. Start Debug Session

Press `F5` or use the Debug view to start a debugging session. The debugger will connect to your z/TPF system.

### 3. Control Execution

Use the debug toolbar to control execution:
- **Continue** (`F5`): Resume execution
- **Step Over** (`F10`): Execute current line
- **Step Into** (`F11`): Step into function calls
- **Step Out** (`Shift+F11`): Step out of current function

---

## Inspecting Variables

### Variables View

The Variables view shows:
- Local variables
- Function parameters
- Register values
- Memory contents

### Watch Expressions

Add expressions to the Watch view to monitor specific values during debugging.

### Debug Console

Use the Debug Console to:
- Evaluate expressions
- Execute debug commands
- View output and logs

---

## Debug Commands

Access these commands via the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`):

| Command | Description |
|---------|-------------|
| `z/TPF Debug: Start Debugging` | Start a debug session |
| `z/TPF Debug: Stop Debugging` | Stop the current debug session |
| `z/TPF Debug: Restart` | Restart the debug session |
| `z/TPF Debug: Toggle Breakpoint` | Add/remove breakpoint at current line |

---

## Keyboard Shortcuts

Default debugging shortcuts:

| Shortcut | Action |
|----------|--------|
| `F5` | Start/Continue debugging |
| `F9` | Toggle breakpoint |
| `F10` | Step over |
| `F11` | Step into |
| `Shift+F11` | Step out |
| `Shift+F5` | Stop debugging |

---

## Debugging Tips

- **Conditional Breakpoints**: Right-click a breakpoint to add conditions
- **Logpoints**: Add log messages without stopping execution
- **Call Stack**: Use the Call Stack view to navigate execution context
- **Breakpoint Management**: Use the Breakpoints view to enable/disable breakpoints

---

## Next Steps

- Explore [Features](features.md) for more debugging capabilities
- Report issues on [GitHub](https://github.com/IBM/ztpf-debugger/issues)