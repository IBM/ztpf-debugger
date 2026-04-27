# IBM z/TPF Debugger

IBM z/TPF Debugger is an extension for Visual Studio Code that allows you to debug z/TPF programs that run on IBM z/TPF.

# Issues

Any [issues](https://github.com/IBM/ztpf-debugger/issues) reported directly on this repository will be handled on a best-effort basis by the development team. Priority will be given to issues reported via opening a case through the [IBM Support](https://www.ibm.com/mysupport/s/createrecord/NewCase) channel.

# License
- The license for IBM z/TPF Debugger can be found in the [LICENSE file](https://github.com/IBM/ztpf-debugger/blob/main/product/LICENSE) in the product folder in this repository.
- All other files managed in this repository are intended for the purpose of presenting the [product documentation web site](https://IBM.github.io/ztpf-debugger). The license for these files can be found in the [LICENSE file](https://github.com/IBM/ztpf-debugger/blob/main/LICENSE) in the root folder of this repository.

## Core Capabilities

### 1. Remote Debug Registration

The extension enables registration of debug hooks on the z/TPF runtime system:

- **Program Registration**: Register debug hooks for specific z/TPF programs by name
- **Session Management**: Create, manage, and terminate debug registration sessions
- **Real-time Notifications**: Receive status updates when registration succeeds or fails
- **Automatic GDB Launch**: Automatically starts GDB debug sessions when hooks are triggered

### 2. Secure Communication

Robust network communication with the remote debug service:

- **TLS/SSL Support**: Secure connections enabled by default using Transport Layer Security
- **Certificate Management**: Support for custom server certificates appended to trusted CA list
- **Non-secure Mode**: Optional fallback to non-encrypted connections when needed
- **Connection Validation**: Comprehensive validation of connection parameters before establishing sessions

### 3. Debug Configuration

Flexible configuration system integrated with Visual Studio Code's launch.json:

- **Schema Validation**: Built-in JSON schema validation for debug configurations
- **Configuration Snippets**: Pre-built templates for common debugging scenarios
- **IntelliSense Support**: Auto-completion and documentation for all configuration properties
- **Multiple Registration Types**: Support for program, function, macro, and error-based registration (program type currently implemented)

### 4. GDB Integration

Seamless integration with the GNU Debugger (GDB):

- **SSH Pipe Transport**: Connects to remote GDB instances via SSH tunneling
- **Automatic Configuration Generation**: Dynamically creates GDB launch configurations
- **Source File Mapping**: Maps remote source paths to local workspace paths
- **Shared Object Search Paths**: Configurable paths for locating required shared libraries
- **TPFGDB Support**: Integration with z/TPF-specific GDB extensions

---

## Configuration Options

### Required Extension Settings

Users must configure these settings for the extension to function:

| Setting | Description |
|---------|-------------|
| `ztpf-debugger.pipe.program` | Absolute path to SSH executable on local workstation |
| `ztpf-debugger.pipe.user` | Username for SSH authentication to Linux on IBM Z system |
| `ztpf-debugger.pipe.host` | IP address or hostname of Linux on IBM Z system |
| `ztpf-debugger.tpfgdb.path` | Absolute remote path to TPFGDB executable on Linux on IBM Z system |
| `ztpf-debugger.tpfgdb.pythonPath` | Absolute remote path to TPFGDB Python script on Linux on IBM Z system |

### Optional Extension Settings

| Setting | Default | Description |
|---------|---------|-------------|
| `ztpf-debugger.pipe.debuggerPath` | `/usr/bin/gdb` | Absolute remote path to GDB executable on Linux on IBM Z system |
| `ztpf-debugger.TLS.serverCertificate` | `null` | Path to additional server certificate for TLS |

### Launch Configuration Properties

#### Required Properties

- **`hostName`**: IP address or hostname of debug server
- **`port`**: Port number the debug server listens on
- **`options`**: Registration configuration object (type-specific)

#### Optional Properties

- **`secure`** (default: `true`): Enable/disable TLS encryption
- **`additionalSOLibSearchPath`**: Array of remote paths to search for shared objects
- **`sourceFileMap`**: Object mapping remote source paths to local paths

---

## System Requirements

### Local Workstation

- **Visual Studio Code**: Version 1.105.1 or higher
- **SSH Client**: Installed and configured with public/private key authentication
- **Extension Dependency**: Microsoft C/C++ extension (`ms-vscode.cpptools`)

### Remote System

- **Platform**: Linux on IBM Z
- **GDB**: GNU Debugger installed and accessible
- **z/TPF Runtime**: Debug server feature installed and running
- **TPFGDB**: z/TPF-specific GDB extensions installed on Linux on IBM Z system

---

## Known Limitations

1. **Registration Types**: Currently only program-based registration is implemented
2. **Language Support**: Only C/C++ programs are supported for debugging

---
