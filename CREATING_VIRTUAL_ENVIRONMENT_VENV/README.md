## CRIANDO AMBIENTE VIRTUAL

### 1) Criar o Ambiente Virtual (venv) (alterar o x para a versão do seu Python):
```
python3.x -m venv venv
```

### 2) Ativando o Ambiente Virtual (venv):

Linux:
```. venv/bin/activate```
ou:
```source venv/bin/activate```

Windows (PowerShell):
```.\venv\Scripts\Activate.ps1```

Windows (CMD):
```.\venv\Scripts\activate.bat```

### 3) (WINDOWS) Se apresentar algum erro de permissão, siga o passo abaixo:

    - Abrir o PowerShell como Administrador;
    - Digitar o comando: Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
    - Fechar o terminal e abrir novamente. Provalmente vai funcionar.

### 4) Desativando Ambiente Virtual (venv):
```
deactivate
```