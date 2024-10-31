# Hello Dev Container with Jupyter

I know that many Python developers use **Jupyter**. I have just started learning Python, but I use Jupyter to check the operation because it is useful.

The sample in this repository is a sample of running Jupyter in a Docker container and accessing and using that environment from VS Code.

## DevContainer Usage

This repository contains a [DevContainer](https://containers.dev) setup which provides an isolated development environment with the necessary tools and configurations to develop with **Jupyter** notebook. It utilizes Docker to provide a consistent and reproducible development environment.

### Prerequisites

In order to leverage this DevContainer, the following prerequisites are needed:

- Install [Docker Desktop](https://www.docker.com/) (Windows & MacOS) or docker engine in [Linux](https://docs.docker.com/engine/install/)
- Install [Visual Studio Code](https://code.visualstudio.com/) and the [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension
- Install Git and clone this repository
- If you're on Windows, we recommend you do this within WSL2 for disk-I/O performance reasons. Install the [WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) VSCode extension too.

!!! Important. The latest Docker version includes docker-compose as a plugin.
So, if you are using latest version of the Docker please make sure that you not just have installed docker-compose but the "compose" plugin to the docker as well.
https://docs.docker.com/compose/install/linux/

### Start-up instructions

To boot up this DevContainer, simply run the `Reopen in Container` action. You can do this in three different places

- There may be an automatic popup in the bottom-right prompting you with a button
- The `><` button in the bottom-left corner + menu-option in the top-center
- Search for it in the command palette

Separate configurations are provided to simulate different environments you would like to target for this project's dependencies. Choose which you'd like to use, and the appropriate DevContainer will launch.

## Export Jupyter notebook to PDF

The original intention of this Devcontainer was to have quick and lightweight way to get **Jupyter** work with Java support to do some quick experiments.
The Java itself makes need to download a lot to initialize the container so it is not so "lightweight" anymore.

So, notebook export to HTML works but to export to PDF you need extra dependencies to be installed. Those dependencies are bringing a lot of transitional dependencies which makes the first time Devcontainer run even more heavy. So, right now, it is disabled by default. You can enable it in the [Dockerfile](.devcontainer/Dockerfile):

```code
...
RUN apt-get install -y jupyter-notebook

# !!! Uncomment this to have Jupyter export to PDF work:
# RUN apt-get install -y texlive-xetex texlive-fonts-recommended texlive-plain-generic jupyter-nbconvert

```

After that you will need to rebuild the Devcontainer.
