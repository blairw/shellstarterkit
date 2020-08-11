# Terminal and Package Manager Setup

## Navigation

- Terminal and Package Manager Setup (**Mac**, [Windows](01-terminal-setup-win.md))
- [UNIX-based Command Line Basics](02-unix-basics.md)
- [Python Environment Setup](03-python-setup.md)
- [Python web server](04-python-web-server.md)

## Start with Terminal

MacOS already comes with a UNIX-based command line via **Terminal.app**, which is fantastic. To launch it, open the macOS Launchpad and search for **Terminal**.

## Install Homebrew

Homebrew is the most common and straightforward way to install additional command line programs on Mac. It can also automate the installation of regular Mac apps that are not offered through the App Store (this includes most programming-focused apps).

To install Homebrew, follow the instructions at: https://brew.sh/. Note that you will need administrator access to your Mac.

Once you have Homebrew installed, you can install - for example - rclone:

```bash
brew install rclone
```

## Install VSCodium

VSCodium will make editing lots of files inside a folder a lot easier. This is great for organising projects.

Assuming you've installed Homebrew, you can install VSCodium simply by running:

```bash
brew cask install vscodium
```

## Switch to zsh

If you haven't already, make sure you switch to `zsh` - it does everything that `bash` can do, but [has Apple's blessing](https://support.apple.com/en-us/HT208050). To do this:

```bash
chsh -s /bin/zsh
```

## oh-my-zsh with Powerlevel10k

Now install **oh-my-zsh** to make your Terminal prompt more useful - follow the instructions at https://ohmyz.sh/. 

Once oh-my-zsh installed, get the Powerlevel10k theme:

```bash
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
brew cask install font-blexmono-nerd-font
curl https://raw.githubusercontent.com/blairw/shellstarterkit/master/dot-p10k.zsh -o ~/.p10k.zsh
```

Now edit the zshrc file:

```bash
code ~/.zshrc
```

In the file that opens, find the line starting with `ZSH_THEME` and set it to:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

At the end of the file, add:

```bash
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh
```