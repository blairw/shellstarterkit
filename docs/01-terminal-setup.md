# Terminal and package manager setup

## Navigation

1. **[Terminal and package manager setup](docs/01-terminal-setup.md)**
    1. [macOS](#macos)
    2. Windows  
2. _[Python environment setup](docs/02-python-setup.md)_
3. _[Python web server](docs/03-python-web-server.md)_

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