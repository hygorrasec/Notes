## TUTORIAL DJANGO:

### 1) Criando projeto:

```
mkdir project01
cd project01
```

### 2) Abrindo o projeto no VSCode:

```
code .
```

### 3) Criar Ambiente Virtual (alterar o x para a versão do seu Python):
```
python3.x -m venv venv
```

### 4) Ativando o Ambiente Virtual (venv):

Linux:
```. venv/bin/activate```
ou:
```source venv/bin/activate```

Windows:
```\venv\Scripts\activate```

### 5) Anotações:

    - As rotas são configuradas no arquivo urls.py
    - Para criar um novo app (página), usar o comando: python manage.py startapp NOME_DO_APP
    - A pasta do app contém algumas pastas e arquivos.
    - Pasta Migrations: Relacionado as migrações da Base de Dados (ORM do Django).
    - Arquivo __init__.py: Serve para indicar pro Python que existe um pacote e outras coisas...
    - Arquivo admin.py: Para registrar os Models e fazer as configurações necessários. Também serve como ORm do Django.
    - Arquivo apps.py: Basicamente registra o nome do app.
    - Arquivo tests.py: Para testar a aplicação.
    - Arquivo views.py: Mostrar o que será exibido como response.
    - Criamos um arquivo urls.py dentro do diretório do app, para as rodas locais do app.
    - Dentro do urls.py do projeto, incluímos a função include para importar as urls.py dos apps.
    - Criamos uma pasta chamada templates dentro da pasta do app criado. O Django busca arquivos dentro desta pasta.
    - Precisamos atualizar o settings.py em INSTALLED_APPS o nome do app que adicionamos. O nome está dentro do arquivo apps.py de cada app.
    - Precisamos adicionar namespace (uma pasta) dentro da pasta templates da pasta do app. Normalmente o nome é o mesmo do app. E dentro deste namespace colocamos os arquivos html.