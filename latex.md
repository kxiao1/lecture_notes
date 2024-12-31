# Getting LaTeX

## Overleaf

Sign up for a free account at [Overleaf](https://www.overleaf.com/).

This was my setup in college. Unfortunately, without a studnet account or some other subscription, projects cannot be linked with Git and their histories cannot be checked.

## Visual Studio Code

### Installing MiKTeX

``MiKTeX`` and ``Tex Live`` are the two main LaTeX distributions. I choose ``MiKTeX`` because I happen to have used it in various settings.

Refer to [instructions](https://miktex.org/download#ubuntu) for each Linux distribution (in my case WSL2 and Ubuntu 22.04):

```bash
curl -fsSL https://miktex.org/download/key | sudo tee /usr/share/keyrings/miktex-keyring.asc > /dev/null
echo "deb [signed-by=/usr/share/keyrings/miktex-keyring.asc] https://miktex.org/download/ubuntu jammy universe" | sudo tee /etc/apt/sources.list.d/miktex.list
sudo apt update && sudo apt install miktex\
miktex-console
```

If opening the GUI fails with the following error:

```console
$ miktex-console
qt.qpa.plugin: Could not find the Qt platform plugin "xcb" in ""
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.
```

then follow the steps given [here](https://github.com/MiKTeX/miktex/issues/1469):

```bash
sudo apt install qt6-wayland
sudo apt install qt6-qpa-plugins
```

### Setting up LaTeX workshop

Reference: [Jia Jia](https://mathjiajia.github.io/vscode-and-latex/)

Now pressing ``Ctrl+Alt+B`` will recompile a TeX file. The file will also be recompiled when it is saved. If needed, press ``Ctrl+Shift+P`` and select ``Build With Recipe`` e.g. when working with ``BibTex`` files.
