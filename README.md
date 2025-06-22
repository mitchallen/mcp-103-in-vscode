# MCP Time in VS Code Demo

This project demonstrates how to use the Model Context Protocol (MCP) to access time-related services directly within Visual Studio Code. It uses a Docker-based MCP server to provide current time and timezone conversion features.

## Features
- Query the current time in any timezone using MCP commands.
- Convert times between different timezones.
- Easily integrate with VS Code for a seamless developer experience.

## Prerequisites
- [Docker](https://www.docker.com/) installed and running
- Visual Studio Code
- MCP extension or compatible setup

## Setup
1. Clone this repository.
2. Ensure Docker is running on your machine.
3. The `.vscode/mcp.json` file is preconfigured to use the `mcp/time` Docker image:

```jsonc
{
    "servers": {
        "time": {
            "command": "docker",
            "args": [
                "run",
                "-i",
                "--rm",
                "mcp/time"
            ]
        }
    }
}
```

> **Note:** The MCP server configuration can be either global (shared across all projects) or local (specific to this project). This demo keeps the MCP server configuration local by placing the `mcp.json` file in the `.vscode` directory of the project. This ensures the time service setup is isolated to this workspace and does not affect other projects or global settings.
> 
> **Version Control:** The included `.gitignore` ensures that the `.vscode` folder and the `mcp.json` configuration file are tracked in version control, so your project-specific MCP settings are always included.

4. Open the project in VS Code.
5. Use the MCP commands to query the current time or perform timezone conversions.

## Usage Examples

```prompt
What time is it in Boston?
```

```prompt
What time is it in Vegas?
```

## Notes
- The `mcp/time` Docker image is pulled automatically if not present.
- All time queries are processed in real-time using the Docker container.

## License
MIT
