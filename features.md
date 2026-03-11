---
title: Features
layout: default
nav_order: 4
---

# Debugger Features

Explore the debugging features of the z/TPF VS Code Debugger Extension.

{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Breakpoint Management

### Standard Breakpoints

Set breakpoints to pause execution:

- Click in the gutter to add/remove breakpoints
- Press `F9` to toggle breakpoint on current line
- Breakpoints persist across debug sessions
- Enable/disable breakpoints without removing them

### Conditional Breakpoints

Break only when conditions are met:

- Right-click breakpoint to add condition
- Use expressions to control when to break
- Useful for debugging loops and specific scenarios

### Logpoints

Log messages without stopping execution:

- Add log messages at specific points
- View output in Debug Console
- No need to modify source code

---

## Step Execution

### Execution Control

Control program execution:

- **Continue** (`F5`): Resume execution until next breakpoint
- **Step Over** (`F10`): Execute current line, skip function calls
- **Step Into** (`F11`): Step into function calls
- **Step Out** (`Shift+F11`): Complete current function and return
- **Restart** (`Ctrl+Shift+F5`): Restart debug session
- **Stop** (`Shift+F5`): Stop debugging

### Execution Flow

Navigate through your code:

- Pause execution at any time
- Resume from breakpoints
- Step through code line by line
- Skip over or dive into functions

---

## Variable Inspection

### Variables View

Inspect variables during debugging:

- View local variables
- Examine function parameters
- Monitor register values
- Inspect memory contents
- Expand complex data structures

### Watch Expressions

Monitor specific values:

- Add expressions to watch
- Evaluate custom expressions
- Track values across execution
- Update in real-time

---

## Call Stack

### Stack Navigation

View and navigate the call stack:

- See the current execution path
- Navigate between stack frames
- View function call hierarchy
- Inspect variables at each level

---

## Debug Console

### Interactive Debugging

Use the Debug Console to:

- Evaluate expressions during debugging
- Execute debug commands
- View program output
- Inspect values on-the-fly
- Test expressions before adding to watch

### Console Commands

Common debug console operations:

- Evaluate variables
- Call functions
- Modify values
- View memory
- Execute system commands

---

## Debug Configuration

### Launch Configuration

Configure debugging in `.vscode/launch.json`:

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

### Configuration Options

- **program**: Path to the program to debug
- **stopOnEntry**: Pause at program entry
- **args**: Command line arguments
- **env**: Environment variables

---

## Support

For help and support:

- Report issues on [GitHub Issues](https://github.com/IBM/ztpf-debugger/issues)
- View documentation for detailed guides