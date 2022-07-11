## INSTALANDO QUALQUER VERSÃO DO JAVA:

### 1) Baixar o java mais recente:

https://www.oracle.com/java/technologies/downloads
	
### 2) Criar uma pasta no diretório /home chamado "apps", depois descompactar o java baixado dentro desse diretório (sugiro renomear a pasta para jdk_x, onde x é a versão baixada).
	
### 3) Adicionar no final do arquivo .bashrc que está no diretório /home (Ctrl + H pra mostrar os arquivos e pastas ocultas):
```
# Configuração Java
JAVA_HOME=/home/NOME_DO_USUARIO/apps/jdk_18
export JAVA_HOME

PATH=$PATH:$JAVA_HOME/bin
export PATH
```

### 4) Abra um novo terminal e confira se o java foi instalado corretamente.
```
java --version
```