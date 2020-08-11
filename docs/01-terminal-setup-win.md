# Terminal and Package Manager Setup

## Navigation

- Terminal and Package Manager Setup ([Mac](01-terminal-setup-mac.md), **Windows**)
- [UNIX-based Command Line Basics](02-unix-basics.md)
- [Python Environment Setup](03-python-setup.md)
- [Python web server](04-python-web-server.md)

## Install WSL

Windows does not come with a UNIX-compatible command line by default (it does have `cmd` and `powershell`, but these are DOS-based, not UNIX-based). However, if you are running the latest version of Windows 10, you can install the Windows Subsystem for Linux (WSL).

Please refer to the WSL installation instructions at: https://docs.microsoft.com/en-us/windows/wsl/install-win10

- ⚠️ Please make sure that you follow the instructions for WSL 1, not WSL 2 (this has not been thoroughly tested on Windows 10 for older computers).
- 👍 It is recommended that you also install [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701).

Once you have WSL installed, please installed **Ubuntu 18.04 LTS**. Please do **not** use Ubuntu 20.04 LTS as this only works properly on WSL 2.

## Switch to zsh

If you haven't already, make sure you switch to `zsh`. To do this:

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


## Allow Git to save credentials

Once WSL 1, Ubuntu 18.04 LTS and Windows Terminal are installed, open Ubuntu using Windows Terminal and run:

```bash
git config --global credential.helper store
```

Warning: This stores credentials in a plaintext file on your computer. If you are concerned, you should turn on BitLocker. See https://support.microsoft.com/en-au/help/4028713/windows-10-turn-on-device-encryption