---
title: Configuration
layout: default
nav_order: 5
---

# Configuration Guide

Learn how to configure the z/TPF VS Code Debugger Extension.

{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Debug Configuration

### Launch Configuration

Create a `.vscode/launch.json` file in your project:

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

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `name` | string | - | Display name for the configuration |
| `type` | string | `"ztpf"` | Debugger type (must be "ztpf") |
| `request` | string | `"launch"` | Request type (launch or attach) |
| `program` | string | - | Path to the program to debug |
| `stopOnEntry` | boolean | `false` | Pause at program entry point |
| `args` | array | `[]` | Command line arguments |
| `cwd` | string | `"${workspaceFolder}"` | Working directory |

---

## Connection Settings

### System Connection

Configure your z/TPF system connection in settings:

1. Open Settings: `Ctrl+,` (Windows/Linux) or `Cmd+,` (macOS)
2. Search for **"z/TPF"**
3. Configure connection details

Or edit `settings.json`:

```json
{
  "ztpf.debug.host": "your-ztpf-host.example.com",
  "ztpf.debug.port": 8001,
  "ztpf.debug.timeout": 30000
}
```

### Authentication

Configure authentication:

```json
{
  "ztpf.debug.username": "your-username",
  "ztpf.debug.authMethod": "password"
}
```

{: .warning }
> **Security Note**: Credentials are stored securely in VS Code's credential store.

---

## Breakpoint Settings

### Breakpoint Configuration

Configure breakpoint behavior:

```json
{
  "ztpf.debug.breakpoints.validateOnStart": true,
  "ztpf.debug.breakpoints.allowConditional": true
}
```

### Conditional Breakpoints

Set conditions for breakpoints:

1. Right-click on a breakpoint
2. Select **"Edit Breakpoint"**
3. Enter a condition expression

Example conditions:
- `counter > 100`
- `status == "error"`
- `index % 10 == 0`

---

## Debug Output Settings

### Output Configuration

Configure debug output:

```json
{
  "ztpf.debug.showConsole": true,
  "ztpf.debug.showVariables": true,
  "ztpf.debug.showCallStack": true,
  "ztpf.debug.verbosity": "normal"
}
```

**Verbosity Levels:**
- `minimal` - Essential information only
- `normal` - Standard debug output
- `verbose` - Detailed debug information

---

## Example Configurations

### Basic Configuration

Minimal setup for debugging:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug z/TPF",
      "type": "ztpf",
      "request": "launch",
      "program": "${file}"
    }
  ]
}
```

### Advanced Configuration

Configuration with additional options:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug z/TPF (Advanced)",
      "type": "ztpf",
      "request": "launch",
      "program": "${file}",
      "stopOnEntry": true,
      "args": ["--verbose"],
      "cwd": "${workspaceFolder}",
      "env": {
        "DEBUG": "true"
      }
    }
  ]
}
```

### Multiple Configurations

Define multiple debug configurations:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Current File",
      "type": "ztpf",
      "request": "launch",
      "program": "${file}"
    },
    {
      "name": "Debug Main Program",
      "type": "ztpf",
      "request": "launch",
      "program": "${workspaceFolder}/src/main.asm"
    },
    {
      "name": "Debug with Stop on Entry",
      "type": "ztpf",
      "request": "launch",
      "program": "${file}",
      "stopOnEntry": true
    }
  ]
}
```

---

## Workspace Settings

### Project-Specific Settings

Configure settings for your workspace in `.vscode/settings.json`:

```json
{
  "ztpf.debug.host": "ztpf-dev.example.com",
  "ztpf.debug.port": 8001,
  "ztpf.debug.showConsole": true,
  "ztpf.debug.verbosity": "normal"
}
```

---

## Troubleshooting

### Connection Issues

If you can't connect to the debugger:

1. Verify host and port settings
2. Check network connectivity
3. Confirm firewall settings
4. Validate credentials

### Configuration Validation

Validate your configuration:

1. Open Command Palette (`Ctrl+Shift+P`)
2. Run **"z/TPF Debug: Validate Configuration"**
3. Review any errors or warnings

---

## Next Steps

- Review [Getting Started](getting-started.md) for debugging basics
- Explore [Features](features.md) for debugging capabilities
- Report issues on [GitHub](https://github.com/IBM/ztpf-debugger/issues)