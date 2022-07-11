## INSTALANDO QUALQUER VERSÃO DO PYTHON:

### 1) Atualizar o Sistema:
```
sudo apt-get update
sudo apt-get upgrade -y
```

### 2) Instalar as dependências:
```
sudo apt install build-essential zlib1g-dev libjpeg-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev sqlite3 liblzma-dev curl libbz2-dev
```

### 3) Baixar o Python mais recente e descompactar:
	
https://www.python.org/downloads

### 4) Com o terminal aberto no diretório do python baixado, executar os comandos um de cada vez:
```
./configure --enable-optimizations --with-ensurepip=install
make -j 2
sudo make altinstall
```

### 5) Verifique se foi instalado corretamente (alterar o x para a versão que foi instalada):
```
python3.x --version
pip3.x --version
```

### 6) Atualizar o pip:
```
sudo pip3.x install --upgrade pip
```