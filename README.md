# Mac setup for web development [2025]

## Command Line developer tools

```
xcode-select --install
```

## Homebrew

Install [Homebrew](https://brew.sh/) as package manager for macOS

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Install apps via homebrew

```
brew install --cask \
 raycast \
 bitwarden \
 google-chrome \
 firefox \
 brave-browser \
 iterm2 \
 visual-studio-code \
 docker \
 rectangle \
 figma \
 imageoptim \
 maccy
```

## Install terminal applications

```
brew install \
 wget \
 git \
 yarn \
 terminal-notifier \
 pnpm
```

## Shell

It's up to you to install [iTerm2](https://iterm2.com/) or [Hyper](https://hyper.is/), both can work with zsh as default shell.

Install Oh My Zsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Update Oh My Zsh

```
omz update
```

Reload configuration

```
source ~/.zshrc
```

Install Hack Nerd Fonts for font ligatures in iTerm or VSCode/Cursor

```
brew install --cask font-hack-nerd-font
```

ZSH aliases

```
# edit global zsh configuration

alias zshconfig="code ~/.zshrc"

# reload zsh configuration

alias reload="source ~/.zshrc"

# edit global git configuration

alias gitconfig="code ~/.gitconfig"

# clean homebrew and update all packages

alias brewski='brew update && brew upgrade && brew cleanup; brew doctor; brew missing; echo "Brewski Complete" | terminal-notifier -sound default -appIcon https://brew.sh/assets/img/homebrew-256x256.png -title "Homebrew"'
```

## Node.js

Use [NVM](https://github.com/nvm-sh/nvm) to install Node.js and switch between Node versions.

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Install the latest version

```
nvm install node
```

Restart terminal and run this command

```
nvm use node
```

Confirm that you have installed the latest version of Node and npm

```
node -v && npm -v
```

Update nvm

```
nvm install node --reinstall-packages-from=node
```

Install npm to latest version

```
npm install -g npm@latest
```

Change Node version

```
nvm install xx.xx
nvm use xx.xx
```

Set default version

```
nvm alias default xx.xx
```

## Git

### Configure user identity

Set your name and email for commit identification:

```
git config --global user.name "Your Name"
git config --global user.email "you@email.com"
```

### Create a better git log format

Add a helpful alias for cleaner log output:

```
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

You can use the git log command with this alias:

```
git lg
```

### Set default branch name

Set the default branch to main instead of master:

```
git config --global init.defaultBranch main
```

### View configuration

Print your global git configuration:

```
git config --list
```

## System Preferences (Terminal)

Override system preferences from the terminal if needed

```
# take screenshots as jpg (usually smaller size) and not png

defaults write com.apple.screencapture type jpg

# do not open previous previewed files (e.g. PDFs) when opening a new one

defaults write com.apple.Preview ApplePersistenceIgnoreState YES

# show Library folder

chflags nohidden ~/Library

# show hidden files

defaults write com.apple.finder AppleShowAllFiles YES

# show path bar

defaults write com.apple.finder ShowPathbar -bool true

# show status bar

defaults write com.apple.finder ShowStatusBar -bool true

# prevent left and right swipe through history in Chrome

defaults write com.google.Chrome AppleEnableSwipeNavigateWithScrolls -bool false

killall Finder;
```
