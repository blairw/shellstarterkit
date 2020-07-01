# Terminal and Package Manager Setup

## Navigation

- **Terminal and Package Manager Setup**
    - [macOS](#macos)
    - Windows  
- [UNIX-based Command Line Basics](02-unix-basics.md)
- [Python Environment Setup](03-python-setup.md)
- [Python web server](04-python-web-server.md)

<a name="macos"></a>
## macOS

MacOS already comes with a UNIX-based command line via **Terminal.app**, which is fantastic. To launch it, open the macOS Launchpad and search for **Terminal**.

### Install Homebrew

Homebrew is the most common and straightforward way to install additional command line programs on Mac. It can also automate the installation of regular Mac apps that are not offered through the App Store (this includes most programming-focused apps).

To install Homebrew, follow the instructions at: https://brew.sh/. Note that you will need administrator access to your Mac.

Once you have Homebrew installed, you can install - for example - rclone:

```bash
brew install rclone
```

### Install VSCodium

VSCodium will make editing lots of files inside a folder a lot easier. This is great for organising projects.

Assuming you've installed Homebrew, you can install VSCodium simply by running:

```bash
brew cask install vscodium
```

### Switch to zsh

If you haven't already, make sure you switch to `zsh` - it does everything that `bash` can do, but [has Apple's blessing](https://support.apple.com/en-us/HT208050). To do this:

```bash
chsh -s /bin/zsh
```

**Optional:** Since we'll be using `zsh`, you might want to install **oh-my-zsh** to make your Terminal prompt more useful - see https://ohmyz.sh/. I personally like to use the **amuse** theme. If you want to set this theme, you can run:

```bash
code ~/.zshrc
```

And then set `ZSH_THEME="amuse"` in the file that opens in VSCodium at this stage.

## Windows

### Install Ubuntu on WSL

Windows does not come with a UNIX-compatible command line by default (it does have `cmd` and `powershell`, but these are DOS-based, not UNIX-based). However, if you are running the latest version of Windows 10, you can install the Windows Subsystem for Linux (WSL).

Please refer to the WSL installation instructions at: https://docs.microsoft.com/en-us/windows/wsl/install-win10

Note that those instructions are quite technical. Perhaps you would prefer a video instead: ["How to Install & Enable WSL in Windows 10 (+ how to access files) by Percy Grunwald"](https://www.youtube.com/watch?v=5RTSlby-l9w)

Once you have WSL installed, please installed **Ubuntu 18.04 LTS**. Please do **not** use Ubuntu 20.04 LTS as this has not been thoroughly tested on Windows 10 WSL for older computers.

### Install Chocolatey