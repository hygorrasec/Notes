## CASOS OPCIONAIS:

> USANDO O ZSH PARA MODIFICAR O TERMINAL

### 1) Instalar e configurar ZSH
```
sudo apt install zsh -y
chsh -s /bin/zsh
zsh
```

### 2) Instalar Oh-my-zsh! : https://ohmyz.sh
```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### 3) Instalar Zsh Syntax Highlighting : https://github.com/zsh-users/zsh-syntax-highlighting
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### 4) Instalar Zsh Autosuggestions : https://github.com/zsh-users/zsh-autosuggestions
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### 5) Instalar Spaceship Prompt : https://github.com/spaceship-prompt/spaceship-prompt
```
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

### 6) Mudar o zshrc:
```
nano ~/.zshrc
ZSH_THEME="spaceship"
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```
_Depois digitar:_
```
source ~/.zshrc
```

### 7) Font optional : https://github.com/pdf/ubuntu-mono-powerline-ttf
```
mkdir -p ~/.fonts
git clone https://github.com/pdf/ubuntu-mono-powerline-ttf.git ~/.fonts/ubuntu-mono-powerline-ttf
fc-cache -vf
```

### 8) Depois aterar o terminal para a font Ubunto Mono for Powerline e reiniciar o computador.