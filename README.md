# AtCoder Python Dev Container

> [!Note]
> [日本語はこちら](README_jpn.md)

This repository provides a ready-to-use VS Code Dev Container for competitive programming on AtCoder.

## Environment
- [Python 3.13 (slim)](https://hub.docker.com/layers/library/python/3.13-slim/images/sha256-cd4cb2ba193c13d36b59f01c9518d709b41b886388c3af2bbe7d7b29f15a303f)
- [online-judge-tools (oj)](https://pypi.org/project/online-judge-tools/)
 with tab completion
- [Jupyter](https://pypi.org/project/jupyter/)
- [Selenium](https://pypi.org/project/selenium/)
 (for silencing warnings on oj use)

## 🚀 Setup Instructions

Follow these steps to get the same development environment on Windows, macOS, or Linux.

1. Install prerequisites

- [Git](https://git-scm.com/)
- [Docker](https://docs.docker.com/get-started/get-docker/)
	- Windows/macOS → install Docker Desktop
	- Linux → install Docker engine via your package manager.
- [Visual Studio Code (VS Code)](https://code.visualstudio.com/)
- Dev Containers extension for VS Code ([See tutorial](https://code.visualstudio.com/docs/devcontainers/containers))

2. Fork this repository

3. Clone repo to local
Open a terminal and run:
```bash
git clone https://github.com/<your-github-username>/Atcoder_Python.git
cd Atcoder_Python
```

4. Open in VS Code
	1.  Launch VS Code.
	2.  Open the cloned folder (File → Open Folder).
	3. If the Dev Containers extension is installed, you’ll see a prompt:
“Reopen in Container”. Click it.
	- Or, open the Command Palette (Ctrl+Shift+P or Cmd+Shift+P on macOS) and run:
“Dev Containers: Reopen in Container”

VS Code will then:
- Build the Docker image from .devcontainer/Dockerfile.
- Mount your project into the container at /workspaces/Atcoder_python.
- Install Python, oj, Jupyter, and Selenium automatically.


> [!WARNING]
Important: work/ folder
> - This repository contains a folder called work/.
> - It is where you should put all your own contest code and notebooks.
> - Before starting to use the container, please delete the existing contents of work/ — those are my solutions, kept here only as an example.
> - Once emptied, the work/ folder will serve as your personal workspace.


## ✅ Usage
Run Python scripts:
`python main.py`


Please refer https://github.com/online-judge-tools/oj

Download a problem with oj:

`oj download https://atcoder.jp/contests/abc999/tasks/abc999_a`

Test locally:
`oj test`

Start JupyterLab (port 8888 will be forwarded automatically):

`jupyter lab --ip=0.0.0.0 --no-browser --NotebookApp.token=''`

## 🐳 Notes
- Always fork → clone your fork so you can push your own solutions to GitHub.
- All code runs inside the container, so your local system stays clean.
- Your workspace is bind-mounted → changes are saved directly in your local files.
- Works on Windows (via WSL2), macOS (Intel/Apple Silicon), and Linux.


## 🙌 Contributing

Feel free to open issues or PRs to improve the environment (e.g., add useful extensions, packages, or helper scripts).