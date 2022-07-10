## INSTALANDO QUALQUER VERSÃO DO JAVA:

### a) Baixar o java mais recente:

https://www.oracle.com/java/technologies/downloads
	
### b) Criar uma pasta no diretório /home chamado "apps", depois descompactar o java baixado dentro desse diretório (sugiro renomear a pasta para jdk_x, onde x é a versão baixada).
	
### c) Adicionar no final do arquivo .bashrc que está no diretório /home (Ctrl + H pra mostrar os arquivos e pastas ocultas):

```
# Configuração Java
JAVA_HOME=/home/NOME_DO_USUARIO/apps/jdk_18
export JAVA_HOME

PATH=$PATH:$JAVA_HOME/bin
export PATH
```

### d) Abra um novo terminal e confira se o java foi instalado corretamente.

```
java --version
```

## INSTALANDO QUALQUER VERSÃO DO PYTHON:

### a) Atualizar o Sistema:

```
sudo apt-get update
```

### b) Instalar as dependências:

```
sudo apt install build-essential zlib1g-dev libjpeg-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev sqlite3 liblzma-dev curl libbz2-dev
```

### c) Baixar o Python mais recente e descompactar:
	
https://www.python.org/downloads

### d) Com o terminal aberto no diretório do python baixado, executar os comandos um de cada vez:

```
./configure --enable-optimizations --with-ensurepip=install
make -j 2
sudo make altinstall
```

### e) Verifique se foi instalado corretamente:

```
python3.x --version
pip3.x --version
```

### f) Atualizar o pip:

```
sudo pip3.x install --upgrade pip
```

## CRIANDO AMBIENTE VIRTUAL NO VSCODE

### 0 - Configurando settings.json do VSCode:

```
{
    "workbench.colorTheme": "Default Dark+",
    "workbench.iconTheme": "material-icon-theme",
    "window.zoomLevel": 0,
    "python.languageServer": "Pylance", // ms-python.vscode-pylance
    "python.testing.unittestEnabled": false, // ms-python.python
    "python.testing.pytestEnabled": true,
    "python.testing.pytestArgs": [], // -x to bail
    "python.linting.flake8Enabled": true,
    "python.linting.mypyEnabled": true,
    "python.linting.pylintArgs": [
      "--load-plugins=pylint_django",
      "--errors-only"
    ],
    "python.formatting.autopep8Args": ["--indent-size=4"],
    "python.defaultInterpreterPath": "venv/bin/python",
    "[python]": {
      "editor.defaultFormatter": "ms-python.python", // ms-python.python
      "editor.tabSize": 4,
      "editor.insertSpaces": true,
      "editor.formatOnSave": true,
      "editor.formatOnType": true,
      "editor.codeActionsOnSave": {
        "source.organizeImports": true
      }
    },
    "[html]": {
      "editor.formatOnSave": true,
      "editor.defaultFormatter": "vscode.html-language-features",
      "editor.quickSuggestions": {
        "other": true,
        "comments": true,
        "strings": true
      }
    },
    "[django-html]": {
      "editor.formatOnSave": false,
      "editor.defaultFormatter": "vscode.html-language-features",
      "editor.quickSuggestions": {
        "other": true,
        "comments": true,
        "strings": true
      }
    },
    "files.associations": {
      "*.js": "javascript",
      "*.jsx": "javascriptreact",
      "*.xml": "html",
      "*.svg": "html",
      "*.html": "html",
      "django-html": "html", // batisteo.vscode-django
      "**/*.html": "html",
      "**/templates/**/*.html": "django-html",
      "**/base_templates/**/*.html": "django-html",
      "**/requirements{/**,*}.{txt,in}": "pip-requirements"
    },
    "emmet.includeLanguages": {
      "django-html": "html", // batisteo.vscode-django
      "javascript": "javascriptreact",
      "typescript": "typescriptreact"
    }
}
```

### 1 - Criar a pasta do projeto e abrir o VSCode nele:

```
mkdir project1
cd project1
python3.10 -m pip install pip setuptools wheel --upgrade
code .
```

### 2 - Criar o ambiente virtual:

```
python3.10 -m venv venv
```

### 3- Ativando o ambiente virtual:

Linux: ```. venv/bin/activate```
ou Linux: ```source venv/bin/activate```
Windows: ```\venv\Scripts\activate```

### 4 - Instalar Django:

```
pip install django
django-admin --version
```

### 5 - Desativando ambiente virtual:

```
deactivate
```

### 6 - Escolher a versão do Python. No VSCode apertar Ctrl+Shift+P e digitar:

```
Select Interpreter
```

### 7 - Instalar as extenções:

```
Python
Django
Material Icon Theme
Color Highlight
```

## CRIANDO AMBIENTE VIRTUAL GLOBAL PARA PYCHARM

### a) Instalar o Virtualenv:

```
sudo pip3.x install virtualenv virtualenvwrapper
```

### b) Configurar um diretório padrão para o virtualenv. Adicionar no final do arquivo .bashrc que está no diretório /home (Ctrl + H pra mostrar os arquivos e pastas ocultas):

```
# Virtualenv
export WORKON_HOME=$HOME/.virtualenvs

export VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3.10
# Observação acima. Para identificar o diretório do Python, digite no terminar: which python3.x (ontem x é a versão do seu Python instalado)

source /usr/local/bin/virtualenvwrapper.sh
```

### c) Abra um novo terminal e crie um novo ambiente virtual:

```
mkvirtualenv NOME_DO_AMBIENTE_VIRTUAL
```

### d) Se tudo deu certo, você estará conectado ao ambiente virtual que foi criado. Para sair, digite o comando abaixo:

```
deactivate
```

### e) Para acessar novamente o ambiente virtual que você criou, digite o comando abaixo:

```
workon NNOME_DO_AMBIENTE_VIRTUAL
```

### f) Para remover um ambiente virtual, digite o comando abaixo:

```
rmvirtualenv NOME_DO_AMBIENTE_VIRTUAL
```

## CRIANDO TOKEN DE ACESSO PESSOAL NO GITHUB:

### a) Na sua conta do GitHub, vá em Setting => Developer settings => Personal access tokens => Generate new token => Preencha o formulário => clique em Generate token => Copie o Token gerado. O TOKEN será algo como:
```ghp_sFhFsSHhTzMDreGRLjmks4Tzuzgthdvfsrta```

### b) No terminal digite (altere com seus dados):

```
git remote set-url origin https://TOKEN@github.com/YOUR-USERNAME/REPOSITORY
```

### c) Para Linux, você precisa configurar o cliente Git local com um nome de usuário e endereço de e-mail:

```
git config --global user.name "your_github_username"
git config --global user.email "your_github_email"
```

### d) Depois que o Git estiver configurado, podemos começar a usá-lo para acessar o GitHub.

## CRIANDO CHAVE SSH GITHUB:

### a) Na pasta do projeto, configurar:

```
git config --global user.name "your_github_username"
git config --global user.email "your_github_email"
git config --global init.defaultBranch main
git init
```

### b) Criando chave SSH do usuário:

```
ssh-keygen
```

### c) Pegar a chave:

Linux: ```cat /Users/USER_NAME/.ssh/id_rsa.pub```

### d) Copiar a chave e adicionar no Github:

```
Entrar em Settings > SSH and GPG Keys > New SSH key > Colar a chave e salvar
```

### e) Criar um novo repositório no Github utilizando SSH.

## CASOS OPICIONAIS:
>USANDO O ZSH PARA MODIFICAR O TERMINAL

### Instalar e configurar ZSH
```
sudo apt install zsh -y
chsh -s /bin/zsh
zsh
```

### Instalar Oh-my-zsh! : https://ohmyz.sh
```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Instalar Zsh Syntax Highlighting : https://github.com/zsh-users/zsh-syntax-highlighting
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### Instalar Zsh Autosuggestions : https://github.com/zsh-users/zsh-autosuggestions
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### Instalar Spaceship Prompt : https://github.com/spaceship-prompt/spaceship-prompt
```
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

### Mudar o zshrc:
```
nano ~/.zshrc
ZSH_THEME="spaceship"
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```
_Depois digitar:_
```
source ~/.zshrc
```

### Font optional : https://github.com/pdf/ubuntu-mono-powerline-ttf
```
mkdir -p ~/.fonts
git clone https://github.com/pdf/ubuntu-mono-powerline-ttf.git ~/.fonts/ubuntu-mono-powerline-ttf
fc-cache -vf
```

### Depois aterar o terminal para a font Ubunto Mono for Powerline e reiniciar o computador.