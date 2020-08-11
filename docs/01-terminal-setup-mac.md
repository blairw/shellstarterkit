# Terminal and Package Manager Setup

## Navigation

- Terminal and Package Manager Setup (**Mac**, [Windows](01-terminal-setup-win.md))
- [UNIX-based Command Line Basics](02-unix-basics.md)
- [Python Environment Setup](03-python-setup.md)

## Start with Terminal

MacOS already comes with a UNIX-based command line via **Terminal.app**, which is fantastic. To launch it, open the macOS Launchpad and search for **Terminal**.

## Install Homebrew

Homebrew is the most common and straightforward way to install additional command line programs on Mac. It can also automate the installation of regular Mac apps that are not offered through the App Store (this includes most programming-focused apps).

To install Homebrew, follow the instructions at: https://brew.sh/. Note that you will need administrator access to your Mac.

Once you have Homebrew installed, you can install - for example - rclone:

```bash
brew install rclone
```

## Set up a folder on your computer to store gitrepos

- This folder must **not** be in a place where it is managed by a cloud provider (e.g. Dropbox, OneDrive)
- I recommend something like `~/00blair/gitrepos` (Mac), i.e. make `00blair` (but with your name) in your home folder, then in that folder, make a folder called `gitrepos`.
- In Finder, you can quickly go to your home folder by opening a Finder window and then Command + SHIFT + G, then type `~` as the folder to go to.

## Clone this repository

```bash
# whatever you had from the previous step
cd ~/00blair/gitrepos

# clone the repository
git clone -v https://github.com/blairw/shellstarterkit
```

## Install Powerline font

In your copy of this repository, go to the `resources` folder, then `Literation Mono NF`, then `Mac` and select all the fonts (Command + A).

Then install the fonts.

If you get a warning that the fonts may have problems, just click **&check; Select All Fonts** and then click **Install Ticked**.

## Install iTerm2

This is a better terminal.

```bash
brew cask install iterm2
```

Once installed, open iTerm and set the following preferences:

- iTerm2 &rarr; Preferences &rarr; Appearance &rarr; General &rarr; Theme &rarr; **Dark**.

- iTerm2 &rarr; Preferences &rarr; Profiles &rarr; Text &rarr; Font &rarr; **LiterationMono Nerd Font Mono**. (And set the font size to 16, unless you prefer tiny text!)

- iTerm2 &rarr; Preferences &rarr; Profiles &rarr; Text &rarr; Use thin strokes for anti-aliased text &rarr; **Never**.

- iTerm2 &rarr; Preferences &rarr; Profiles &rarr; Keys &rarr; Presets ... &rarr; **&check; Natural Text Editing**.

From now on, please use iTerm2 instead of the Mac Terminal.

## Install Visual Studio Code

Visual Studio Code will make editing lots of files inside a folder a lot easier. This is great for organising projects.

Assuming you've installed Homebrew, you can install Visual Studio Code simply by running, at your iTerm terminal:

```bash
brew cask install visual-studio-code
```

Once Visual Studio Code is installed, set the following preferences:

- Visual Studio Code &rarr; Preferences &rarr; Settings &rarr; **Editor: Font Family**.  
Set this to:
    
    ```
    'LiterationMono Nerd Font Mono', Menlo, monospace
    ```

- Visual Studio Code &rarr; Preferences &rarr; **Color Theme**.  
I recommend **Solarized Dark** or **Dark+ (Default)**. I would avoid using the light coloured themes unless you really feel like you need it. (The Powerlevel10k tool we will install later works better in a dark colour theme.)

## Switch to zsh with Powerlevel10k

If you haven't already, make sure you switch to `zsh` - it does everything that `bash` can do, but [has Apple's blessing](https://support.apple.com/en-us/HT208050). To do this:

```bash
chsh -s /bin/zsh
```

Now install **oh-my-zsh** to make your Terminal prompt more useful - see https://ohmyz.sh/. 

Once installed, get the Powerlevel10k theme:

```bash
## get powerlevel10k theme
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k

## get configuration
curl https://raw.githubusercontent.com/blairw/shellstarterkit/master/resources/dot-p10k.zsh -o ~/.p10k.zsh
```

Now edit the zshrc file:

```bash
code ~/.zshrc
```

In the file that opens, find the line starting with `ZSH_THEME` and set it to:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Find the line starting with `plugins=` and set it to:

```bash
plugins=(git virtualenv)
```

At the end of the file, add:

```bash
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh
```

Save the file, and Quit (Command + Q) from iTerm. Now open iTerm again. You will notice that you now have Powerlevel10k installed.