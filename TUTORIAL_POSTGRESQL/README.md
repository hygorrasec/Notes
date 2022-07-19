## Instalando PostgreSQL Linux:

### 1) Comandos de instação:
```
sudo apt update
sudo apt install postgresql postgresql-contrib
```

### 2) Criar um novo usuário:
```
sudo -u postgres createuser --interactive
```

### 3) Acessando pelo terminal. O primeiro faz com que você utilize o usuário postgres e depois o segundo executa o shell:
```
sudo -i -u postgres
psql
```
> \conninfo = Verificar os detalhes de sua conexão
> \l = Ver uma lista de todos os bancos de dados disponíveis
> \du = Ver uma lista de todos os usuários com seus privilégios
> \password postgres = Definindo senha

### 4) Criar uma base de dados:
```
sudo -u postgres createdb blog
```

### 5) Visualização com PgAdmin:
```
sudo curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add

sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'

sudo apt install pgadmin4

sudo /usr/pgadmin4/bin/setup-web.sh
```

### 6) Para rodar Postgres com o Django vamos precisar de um driver chamado psycopg2
```
pip install psycopg2
```

### 7) Alterando banco no Django. Arquivo settings.py em myproject/myproject/:
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': os.environ.get('DB_NAME', 'nome_do_banco'),
        'USER': os.environ.get('DB_USER', 'nome_do_user'),
        'PASSWORD': os.environ.get('DB_PASS', 'senha_do_user'),
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```
