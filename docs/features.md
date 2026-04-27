---
title: Features
layout: default
nav_order: 4
---

# Debugger Features
{: .no_toc }

Explore the debugging features of the z/TPF Visual Studio Code Debugger Extension.

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

## Extension Logging

The extension is integrated into the Visual Studio Code logging feature which allows to change the logging level of a particular extension. Use the `Developer: Set Log Level...` command to change the log level for all of Visual Studio Code or a particular extension. The development team may ask for you to change the logging level to help diagnose problems.
