# fushar's macOS dotfiles

### Install prerequisites

- Install brew: https://brew.sh
- Install iterm2: https://iterm2.com

### Install fonts and color scheme

```
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

### App color themes

- Visual Studio Code: [One Dark Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme)
- Sublime Text: [One Dark](https://packagecontrol.io/packages/Theme%20-%20One%20Dark)

### GCC

```
brew install gcc
cd /opt/homebrew/bin
ln -s g++-14 g++
```

### Java

```
brew install openjdk@11
sudo ln -sfn /opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk
```

### Web development setup

- https://chrisbergeron.com/2021/03/17/MacOS-11-Big-Sur-Nginx-PHP-and-Mysql/

#### phpmyadmin

```
server {
    listen 80;

    server_name phpmyadmin.local;
    root /opt/homebrew/var/www/phpmyadmin;

    index index.php index.html index.htm;

    location ~ \.php$ {
        try_files      $uri = 404;
        fastcgi_pass   127.0.0.1:9000;
        fastcgi_index  index.php;
        fastcgi_param  SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include        fastcgi_params;
    }
}
```
