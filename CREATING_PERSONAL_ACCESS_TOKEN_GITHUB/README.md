## CRIANDO TOKEN DE ACESSO PESSOAL NO GITHUB:

### 1) Na sua conta do GitHub, vá em Setting => Developer settings => Personal access tokens => Generate new token => Preencha o formulário => clique em Generate token => Copie o Token gerado. O TOKEN será algo como:
```ghp_sFhFsSHhTzMDreGRLjmks4Tzuzgthdvfsrta```

### 2) No terminal digite (altere com seus dados):
```
git remote set-url origin https://TOKEN@github.com/YOUR-USERNAME/REPOSITORY
```

### 3) Para Linux, você precisa configurar o cliente Git local com um nome de usuário e endereço de e-mail:
```
git config --global user.name "your_github_username"
git config --global user.email "your_github_email"
```

### 4) Depois que o Git estiver configurado, podemos começar a usá-lo para acessar o GitHub.