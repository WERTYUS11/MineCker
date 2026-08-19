# About MineCker 

[中文](./README.md)|English

### Overview
This mod allows Minecraft Java Edition (NeoForge/Spigot/Paper/Purpur) server operators to execute Docker commands directly from in-game chat. By typing a message starting with `!docker`, the rest of the message is passed to the system’s Docker CLI, and the output (both stdout and stderr) is sent back to the player.

### Features
- **OP Only**: Only players with OP level 4 can use the command.
- **Cross‑platform**: Automatically detects Windows or Linux and uses `cmd /c` or `bash -c` accordingly.
- **Security**: Blocks dangerous symbols (`|`, `&`, `&&`, `;`, `$`, `` ` ``, etc.) to prevent command injection.
- **Full Output**: Captures both standard output and error output. If the command succeeds but produces no output, a friendly message is shown.
- **No Bundled Docker**: The mod does not ship Docker binaries; it relies on a working `docker` command on the host system.

### Usage
1. Ensure `docker ps` works from the server’s command line.
2. Place the mod in the `mods` folder and start the server.
3. Join as an OP and type in chat:**!docker ps**,this will list all running containers.
4. Any Docker subcommand works, for example:
- `!docker images`
- `!docker run hello-world`
- `!docker stop <container-id>`

### Security Notice
- **Use only in trusted environments**: Any OP can run arbitrary Docker commands. Make sure your OP list is fully trusted.
- **Dangerous symbols are blocked** (e.g., `|`, `&&`), but this does not prevent all malicious commands (e.g., `docker rm -f $(docker ps -aq)` is still dangerous). Only grant OP to players you trust.

### Requirements
- Server: Minecraft 1.21.8/1.21.1 + NeoForge Or Minecraft 1.21.x + Spigot/Paper/Purpur
- OS: Windows (with Docker Desktop) or Linux (with Docker Engine, and the server user must have permission to run Docker)
- Docker: Any version that provides a working `docker` command in system PATH.

### Auto‑created Folder
On the first server start, the mod creates a `LocalDockerAPI` folder in the server root directory (can be used for scripts or configurations).

### License & Trademarks
This mod is licensed under the [MIT License]. Docker is a trademark of Docker, Inc. The use of the Docker logo in compliance with [Docker’s media resources guidelines](https://www.docker.com/company/newsroom/media-resources/)

### Other
DeepSeek help me create this mod.Made by MCreator.
If you want to use this lib for you mod, it's very easy, you just need to send a message "!docker (command)"!
