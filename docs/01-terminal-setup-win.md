# Terminal and Package Manager Setup

## Navigation

- Terminal and Package Manager Setup ([Mac](01-terminal-setup-mac.md), **Windows**)
- [UNIX-based Command Line Basics](02-unix-basics.md)
- [Python Environment Setup](03-python-setup.md)

## Install WSL

Windows does not come with a UNIX-compatible command line by default (it does have `cmd` and `powershell`, but these are DOS-based, not UNIX-based). However, if you are running the latest version of Windows 10, you can install the Windows Subsystem for Linux (WSL).

Please refer to the WSL installation instructions at: https://docs.microsoft.com/en-us/windows/wsl/install-manual

- ⚠️ Please make sure that you follow the instructions for WSL 1, not WSL 2 (this has not been thoroughly tested on Windows 10 for older computers).

## Install Ubuntu 18.04 LTS

- Once you have WSL installed, please install **Ubuntu 18.04 LTS** from the Windows Store. Please do **not** use Ubuntu 20.04 LTS as this only works properly on WSL 2.

- Once you have installed Ubuntu 18.04 LTS, please launch it from the start menu. It will invite you to configure it, including the set up of a username and password for Ubuntu. This does not need to be the same as your Windows username and password &mdash; just make sure you can remember what you do set it to!

## Set up Ubuntu to use the AARnet server

**Note: This step should only be run if you are physically located in Australia.** (AARnet is the official internet service provider for Australian universities, and their server is very fast - certainly for those of us located in Australia, this is much faster than connecting the default American server.)

Run the following commands:

```
sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup
sudo sed -i 's|http://archive.ubuntu.com/ubuntu/|http://mirror.aarnet.edu.au/pub/ubuntu/archive/|g' /etc/apt/sources.list
```

## Update Ubuntu
    
- Run `sudo apt-get update && sudo apt-get upgrade` to update all installed Ubuntu software.
- If prompted for a password, please enter the same password that you set up during the configuration of Ubuntu 18.04 LTS.

## Install Cascadia font

This is a special "coding" font made by Microsoft that works well with Powerlevel10k. Go to https://github.com/microsoft/cascadia-code/releases and download the latest release, then install the fonts.

## Install Windows Terminal

Install [Windows Terminal from the Microsoft Store](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701).

Once installed, open it from the start menu. Then use <kbd>Ctrl</kbd> + <kbd>,</kbd> to open the settings. Then:

- In the **Startup** item in the menu, set the **Default Profile** to **Ubuntu-18.04**.
- In the **Profiles** section in the menu, click on the **Ubuntu-18.04** item, then click the **Appearance** item and set **Font face** to **Cascadia Code PL**.

## Install Visual Studio Code

Visual Studio Code will make editing lots of files inside a folder a lot easier. This is great for organising projects.

You can install Visual Studio Code from https://code.visualstudio.com/ or if you are using [Chocolatey](https://chocolatey.org/) you can run `cinst -y vscode` at an administrative `cmd` prompt.

Once Visual Studio Code is installed, you will be able to run the command `code` in Ubuntu.

## Switch to oh-my-zsh with Powerlevel10k

Make sure you switch to `zsh`. To do this:

```bash
sudo apt-get install zsh
chsh -s /bin/zsh
```

Now install **oh-my-zsh** to make your Terminal prompt more useful:

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

(If asked if you want to switch your default shell to zsh, type <kbd>Y</kbd> for Yes and then hit <kbd>ENTER</kbd>.)

Once oh-my-zsh installed, get the Powerlevel10k theme:

```bash
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Now edit the zshrc file:

```bash
cd ~
code .zshrc
```

In the file that opens, find the line starting with `ZSH_THEME` and set it to:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Find the line starting with `plugins=` and set it to:

```bash
plugins=(git virtualenv)
```

Then re-open Windows Terminal and follow the instructions.

## Allow Git to save credentials

Open Ubuntu using Windows Terminal and run:

```bash
git config --global credential.helper store
```

Warning: This stores credentials in a plaintext file on your computer. If you are concerned, you should turn on BitLocker. See https://support.microsoft.com/en-au/help/4028713/windows-10-turn-on-device-encryption
