## CRIANDO CHAVE SSH GITHUB:

### 1) Na pasta do projeto, configurar:

```
git config --global user.name "your_github_username"
git config --global user.email "your_github_email"
git config --global init.defaultBranch main
git init
```

### 2) Criando chave SSH do usuário:

```
ssh-keygen
```

### 3) Pegar a chave:

Linux: ```cat /Users/USER_NAME/.ssh/id_rsa.pub```

### 4) Copiar a chave e adicionar no Github:

```
Entrar em Settings > SSH and GPG Keys > New SSH key > Colar a chave e salvar
```

### 5) Criar um novo repositório no Github utilizando SSH.