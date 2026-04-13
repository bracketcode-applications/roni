# Roni
![Preview](https://stagingproject.com/previews/ronni-ai.png)
**[View Live Preview](https://roni-ai.stagingproject.com/)**

## Table of Contents

*   [About](#about)
*   [Most Recent Updates](#most-recent-updates)
*   [Dev Tools Utilized](#dev-tools-utilized)
*   [User Instructions](#user-instructions)
    *   [Prerequisites](#prerequisites)
    *   [Build the Image](#build-the-image)
    *   [Run the Container](#run-the-container)
    *   [Useful Podman Commands](#useful-podman-commands)
    *   [Considerations Using Docker](#considerations-using-docker)


## About
This is a containerized, responsive HTML & CSS starter template designed for beginners. It serves as a dual-purpose learning tool: providing a foundation for coding a basic HTML webpage and a practical introduction to containerization using [Podman](https://podman.io/) or [Docker](https://www.docker.com/).

If you are new to the containerization, it is a software packaging technique that wraps an application's code, runtime, libraries, and configuration into a single, lightweight, and portable unit called a container. This ensures the application runs consistently across any computing environment and can also provide a layer of security by providing isolation from the host system.

All code and assets that form part of this project are free-use. Enjoy!

## Most Recent Updates
- Re-coded the project with assistance from Claude and ChatGPT.
- Improved responsive design with added hamburger menu for mobile.
- Added img directory with header background image graphic.
- Containerized the project for Podman.

## Dev Tools Utilized
| | |
| -------- | ------- |
| AI Tool (code):  | ChatGPT 4o, Claude  |
| AI Tool (image):  | Canva AI |
| Containerization:  | Podman |
| Platform: | HTML & CSS    |

## User Instructions

### Prerequisites
This containerized project is intended to be used with [Podman](https://podman.io/). If you dont have Podman, you can follow instructions on their [installation page](https://podman.io/docs/installation).

On Macs, Podman can also be installed via [Homebrew](https://brew.sh/) using the following command.
```
brew install podman
```
Make sure Podman machine (VM) is running. If not use the following command to start one.
```
podman machine init
```
Next you want to start the machine usign the command:
```
podman machine start
```
### Build the Image
From inside your project directory:
```
podman build -t roni .
```

- `-t roni` tags the image with a name
- `.` tells Podman to look for the Containerfile in the current directory

### Run the Container
```
podman run -d -p 8080:80 --name roni-container roni
```
- `-d` runs it in detached (background) mode
- `-p 8080:80` maps port 8080 on your host to port 80 in the container
- `--name` gives the container a friendly name

The site should be visible at: `http://localhost:8080`

### Useful Podman Commands
```
# Check running containers
podman ps

# View logs
podman logs roni-container

# Stop the container
podman stop roni-container

# Remove the container
podman rm roni-container

# Remove the image
podman rmi roni
```

### Considerations Using Docker

Although this project was intended for use with Podman, it can also be utilized with Docker, which is the leading open-source platform for building, shipping, and running applications in containers. Podman is largely a drop-in replacement for Docker, but a couple of things worth knowing:

- Daemonless — Podman runs without a background daemon, so each command is its own process.
- Rootless by default — Podman encourages running containers without root privileges, which is great for security.
- `Containerfile` preferred — While `Dockerfile` works, `Containerfile` is the OCI-standard name Podman prefers.


