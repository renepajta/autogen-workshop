# Autogen Workshop

Welcome to the **Autogen Workshop**! This repository provides hands-on materials and examples for learning and experimenting with [Autogen](https://github.com/microsoft/autogen), a framework for building LLM-powered applications.

## Features

- Pre-configured development environment using **.devcontainers**
- Example notebooks and scripts for Autogen

## Getting Started

### 1. Open in VS Code

1. **Clone this repository:**
   ```pwsh
   git clone https://github.com/renepajta/autogen-workshop.git
   cd autogen-workshop
   ```

2. **Open the folder in [Visual Studio Code](https://code.visualstudio.com/).**

3. **When prompted, reopen in the Dev Container**  
   Or use the Command Palette:  
   `Dev Containers: Reopen in Container`

## Environment Variables

Before running the notebooks or scripts, create your own `.env` file in the project root based on the provided `.env.example` file:

```pwsh
cp .env.example .env
```

Edit the `.env` file to add your API keys or other required environment variables.

### 2. Explore the Workshop

- All dependencies are installed automatically in the dev container.
- Launch Jupyter Notebooks or run scripts directly in the container.
- Use the integrated terminal for running commands.

## Project Structure

- `.devcontainer/` – Dev container configuration files
- `01-intro-to-autogen/` – Introductory notebooks for Autogen basics
- `02-autogen-agents/` – Advanced agent notebooks and examples
- `03-autogen-deepresearch/` – Deep research notebook

## Requirements

- [Docker](https://www.docker.com/) installed
- [Visual Studio Code](https://code.visualstudio.com/) with the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## License

MIT License

---

Happy learning!