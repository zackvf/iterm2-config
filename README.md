# iterm2-config
My personal configuration settings for the macOS terminal replacement iterm2, saved here for easy access on any macbook. Assumes the latest version of Homebrew and Git are already installed.

If Homebrew needs to be added to the macOS PATH, do this before the steps below:
```
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/[username]/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```
# <!-- just a commented-out line here adds the underline bar for a header -->

# Steps to install iterm2, oh my zsh, a zsh theme, and some zsh plugins
## iterm2 installation
```
brew install --cask iterm2
```

> note to self: using '--cask' with the installation is meant for gui application installations, where as using just 'brew install ...' installs a formulae/library/extension, like git, bash, node, etc.

# oh my zsh installation
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

# zsh theme installation - powerlevel10k
```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

# zsh plugin installations
## zsh-autosuggestions
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
> note to self: auto-suggestions displays at least the last visted file location as a suggested location to change directories to

## zsh-syntax-highlighting
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
<br />
update the zsh rc file and reload it:
```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
...
source ~/.zshrc
```