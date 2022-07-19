## Instalando PostgreSQL Linux:

### 1 - Instalando dependências necessários:
```
sudo apt-get update
sudo apt-get install postgresql postgresql-contrib unixodbc unixodbc-dev odbc-postgresql libpq-dev python3-dev psycopg2-binary psycopg2 -y
sudo apt-get upgrade -y
```

### 2 - Criando diretório para armazenamento de dados:
```
sudo mkdir -p /postgres/pgdata/database/data /postgres/pgdata/database/index
```

### 3 - Dando permissão Postgres para os diretórios criado:
```
sudo chown -R postgres /postgres
```

### 4 - Criando uma senha para o usuário postgres:
```
sudo passwd postgres
```

### 5 - Acessar diretório com permissão de acesso:
```
cd /postgres
```

### 6 - Alterar usuário da sessão:
```
su postgres
```

### 7 - Alterar a senha do usuário do banco do postgres (criação de usuário = template1):
```
psql -c "alter user postgres with password 'hygor123'" -d template1
```

### 8 - Criar login de usuário responsável pelo banco de dados:
```
psql -c "create user hygor with login nosuperuser inherit createdb nocreaterole noreplication connection limit -1 password 'hygor123'"
```

### 9 - Criando tablespace de dados do banco de dados da produção:
```
psql -c "create tablespace database_data owner hygor location '/postgres/pgdata/database/data'"
```

### 10 - Criando tablespace de índices do banco de dados da produção:
```
psql -c "create tablespace database_index owner hygor location '/postgres/pgdata/database/index'"
```

### 11 - Criando banco de dados da produção (criação de banco de dados = template0):
```
psql -c "create database database with owner hygor template = template0 encoding = 'WIN1252' lc_collate = 'C' lc_ctype = 'C' tablespace = database_data connection limit - 1"
```

### 12 - Para sair do usuário postgres:
```
exit
```

### 13 - Checar arquivo de instalação de gerenciador obdc:
```
sudo gedit /etc/odbcinst.ini
```

### 14 - Criar coneção odbc:
```
sudo gedit /etc/odbc.ini

[database]
Description=PostgreSQL Conection
Driver=PostgreSQL ANSI
Trace=Yes
TraceFile=/tmp/psqlodbc_database.log
Servername=127.0.0.1
Database=database
UserName=hygor
Password=hygor123
Port=5432
ReadOnly=No
RowVersioning=No
ShowSystemTables=No
ShowOidColumn=No
FakeOidIndex=No
ConnSettings=
```

### 15 - Testando conexão odbc:
```
isql -v database
```

### 16 - Instalando DBeaver:
```
wget https://dbeaver.io/files/22.1.2/dbeaver-ce_22.1.2_amd64.deb -O dbeaver-ce.deb && sudo dpkg -i dbeaver-ce.deb
```

### 17 - Outros comandos dentro do psql:
```
> \conninfo = Verificar os detalhes de sua conexão
> \l = Ver uma lista de todos os bancos de dados disponíveis
> \du = Ver uma lista de todos os usuários com seus privilégios
> \password postgres = Definindo senha
```
