# fushar's macOS dotfiles

### Install prerequisites

- Install brew: https://brew.sh
- Install iterm2: https://iterm2.com

### Install fonts and color scheme

```
brew tap caskroom/fonts
brew install font-hack-nerd-font
ln -s $HOME/dotfiles/iterm2-profile.json $HOME/Library/Application\ Support/iTerm2/DynamicProfiles/
```

### Install oh-my-zsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
rm ~/.zshrc
ln -s $HOME/dotfiles/.zshrc $HOME/
git clone https://github.com/bhilburn/powerlevel9k ~/.oh-my-zsh/custom/themes/powerlevel9k
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
```

Kill all instances of iTerm2, and then restart, and set the Powerlevel9k profile as the default.
