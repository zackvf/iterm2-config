# iterm2-config
My personal configuration settings for the macOS terminal replacement iterm2, saved here for easy access on any macbook. 

Assumes the following are already installed/configured:
- Latest version of Homebrew (best/most widely adopted macOS spm)
- Latest version of git (best/most widely adopted file version control manager, makes installing software from github brainless)
- Latest version of VS Code (not required, just the easiest editor to install for free and use out-of-the-box)
- VS Code configured with "code" command installed in the macOS PATH (lets you open the app from the terminal for quick file editing)

If Homebrew needs to be added to the macOS PATH on a new macbook, do this before the steps below:
```
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/[username]/.zprofile
```
```
eval "$(/opt/homebrew/bin/brew shellenv)"
```

# Steps to install iterm2, oh my zsh, a zsh theme, and zsh plugins
## iterm2 installation (using the regular terminal)
```
brew install --cask iterm2
```

> using '--cask' with the installation is meant for gui application installations, where as using just 'brew install ...' installs a formulae/library/extension, like git, bash, node, etc.

## oh my zsh installation (using iterm2)
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
> curl is the most widely-used data transfer engine for software applications <br />
> read more here: https://curl.se/

## zsh theme installation - powerlevel10k
```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

#### add the theme to the zsh config file and reload it:
```
code ~/.zshrc
```
```
ZSH_THEME="powerlevel10k/powerlevel10k"
```
```
source ~/.zshrc
```
> when prompted, input y to install the meslo nerd font and then restart iterm2 to begin the config process for pl10k 

## zsh plugin installations
### 'zsh-autosuggestions'
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
> displays at least the last visted file location as a suggested location to change directories to

### 'zsh-syntax-highlighting'
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
> highlights terminal commands

#### add the plugins to the zsh config file and reload it:
```
code ~/.zshrc
```
```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
```
```
source ~/.zshrc
```

## additional options and notes
#### set the color theme to a pre-made config
```
curl https://raw.githubusercontent.com/josean-dev/dev-environment-files/main/coolnight.itermcolors --output ~/Downloads/coolnight.itermcolors
```
> post-download, open iterm2 settings > profiles > default > colors > ansi colors color presets > import > select the desired .itermcolors file

#### link to find more color themes
```
https://iterm2colorschemes.com/
```