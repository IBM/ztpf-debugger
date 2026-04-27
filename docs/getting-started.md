---
title: Getting Started
layout: default
nav_order: 3
---
# Getting Started with IBM z/TPF Debugger
{: .no_toc }

This guide will help you get up and running with the IBM z/TPF Debugger Visual Studio Code Extension.

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Quick Start

### Step 1: Install the Extension

Install the extension from the Visual Studio Code Marketplace. See the [Installation Guide](installation.md) for detailed instructions.

### Step 2: Configure Extensions

Configure the required settings for the extension.

| Setting | Description |
| --- | --- |
| `ztpf-debugger.pipe.program` | Local path to an SSH executable |
| `ztpf-debugger.pipe.user` | Linux on IBM Z User ID |
| `ztpf-debugger.pipe.host` | Linux on IBM Z Hostname or IP address |
| `ztpf-debugger.pipe.debuggerPath` | Remote path to the GDB executable |
| `ztpf-debugger.tpfgdb.pythonPath` | Remote path to the tpfgdb.py script |
| `ztpf-debugger.tpfgdb.path` | Remote path to the tpfgdb binary executable |

The IBM z/TPF Debugger extension currently only supports private/public key authentication for SSH. Ensure that you are able to connect to the Linux on IBM Z build environment over SSH.

### Step 3: Configure Debug Connection

1. Open your z/TPF project in Visual Studio Code
2. Create a debug configuration (`.vscode/launch.json`)
3. Configure your z/TPF system connection details and launch conditions

### Step 4: Start Debugging

1. Open a z/TPF source file
2. Set breakpoints by clicking in the gutter
3. Press `F5` to start the current debugger registration profile
4. Start a task on the z/TPF system that will trigger the registration profile
5. The debugger will connect to your z/TPF program

---

## Basic Debugging Workflow

### 1. Set Breakpoints

Click in the gutter (left of line numbers) to set breakpoints where you want execution to pause.

### 2. Start Debug Session

Press `F5` or use the Debug view to start a debugging session. The debugger will connect to your z/TPF system.

### 3. Control Execution

Use the debug toolbar or keyboard shortcuts to control execution:
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
- **Call Stack**: Use the Call Stack view to navigate execution context
- **Breakpoint Management**: Use the Breakpoints view to enable/disable breakpoints

---

## Next Steps

- Explore [Features](features.md) for more debugging capabilities
