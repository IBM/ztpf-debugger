---
title: Configuration
layout: default
nav_order: 5
---

# Configuration Guide
{: .no_toc }

Learn how to configure registration in the IBM z/TPF Debugger Visual Studio Code Extension.

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
      "name": "My Launch Configuration",
      "type": "ztpf",
      "request": "launch",
      "hostName": "example.org",
      "port": 8124,
      "secure": true,
      "sourceFileMap": {
        "/path/to/remote/build/folder": {
          "editorPath": "/path/to/local/workspace/",
          "useForBreakpoints": true
        }
      },
      "additionalSOLibSearchPath": [
        "/path/to/remote/folder/with/solibs"
      ],
      "options": {
        "type": "program",
        "program": "QZZ1"
      }
    }
  ]
}

```

### Configuration Options

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `name` | string | - | Display name for the configuration |
| `type` | string | `"ztpf"` | Debugger type (must be "ztpf") |
| `request` | string | `"launch"` | Request type (must be launch) |
| `hostName` | string | - | Hostname or IP address of the z/TPF system |
| `port` | number | - | Port number for the z/TPF debugger |
| `secure` | boolean | `true` | Whether to use secure (TLS) connection |
| `sourceFileMap` | object | - | Mapping of remote source file paths to local file paths |
| `additionalSOLibSearchPath` | array | - | Additional paths to search for shared libraries on the Linux on IBM Z system |
| `options` | object | - | Additional options for the debugger |

#### sourceFileMap

The paths provided with be substituted in order when trying to resolve the source file locations provided by the debug information contained in the shared object. If the z/TPF application is build in one location and the output is moved to a different location, you should specify the location where the source was built from to match the information contained in the shared object.

If multiple paths are provided, the extended format as shown above may be required to allow for breakpoints to resolve correctly. Otherwise, a shorter `"/path/to/remote/source":/path/to/local/source"` format may be sufficient.

See the [C/C++ extension documentation](https://code.visualstudio.com/docs/cpp/launch-json-reference#_sourcefilemap) for more information.

#### options

The IBM z/TPF Debugger extension currently only supports registering by program name. Support for other registration profiles will follow.

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
      "hostname": "example.org",
      "port": 8214,
      "options": {
        "type": "program",
        "program": "QZZ1"
      }
    }
  ]
}
```

This sends a request to the z/TPF debug server on `example.org` at port `8214` to register the program `QZZ1`.

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
      "hostname": "example.org",
      "port": 8214,
      "secure": false,
      "sourceFileMap": {
        "/path/to/remote/source" : "/path/to/local/source"
      },
      "additionalSOLibSearchPath": [
        "/home/user/out/lib"
      ],
      "options": {
        "type": "program",
        "program": "QZZ1",
      }
    }
  ]
}
```

This sends a request to the z/TPF debug server on `example.org` at port `8214` to register the program `QZZ1`. When the GDB debugger process starts on the Linux on IBM Z system, it will use any shared objects found in the `additionalSOLibSearchPath` directory for symbol resolution. The `sourceFileMap` is used by the Microsoft C/C++ extension to map the source code on the Linux on IBM Z system to the files on the workstation, for example, the paths to the Git clones on the workstation.


### Multiple Configurations

Define multiple debug configurations:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Program 1",
      "type": "ztpf",
      "request": "launch",
      ...
    },
    {
      "name": "Program 2",
      "type": "ztpf",
      "request": "launch",
      ...
    },
    {
      "name": "Program 3",
      "type": "ztpf",
      "request": "launch",
      ...
    }
  ]
}
```

---

## Next Steps

- Review [Getting Started](getting-started.md) for debugging basics
- Explore [Features](features.md) for debugging capabilities
