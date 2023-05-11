
# IGS-Employee-Manager

Este aplicativo foi desenvolvido para gerenciar as informações dos funcionários, como nome, endereço de e-mail e departamento. Consiste em uma API feita com Django e Django Rest Framework




## Instalação

Antes de iniciarmos o projeto, precisamos preparar um ambiente para que tudo funcione. Portanto, após clonar este repositório, crie um ambiente Python e certifique-se de usá-lo. Então precisamos instalar todas as bibliotecas para executá-lo. No projeto temos um arquivo chamado "requirements.txt" e você pode instalar tudo usando o pip. Agora estamos prontos para iniciar o projeto.

Para isso deixei 2 alterantivas, a primeira utilizando o docker-compose e a segunda utilizando um ambiente virtual (venv).

Clone o projeto

```bash
  git clone git@github.com:limawill/IGS-Employee-Manager.git
```


    
## Rodando no docker


Entre no diretório do projeto

```bash
  cd IGS-Employee-Manager
```

Faça o build do docker-compose

```bash
docker-compose build
```

Migre

```bash
docker-compose run backend python manage.py migrate
```

Inicie o servidor

```bash
  docker-compose up
```

Acesse o serviço

```bash
http://localhost:4040/
```
## Virtual (Venv)

Entre no diretório do projeto

```bash
  cd IGS-Employee-Manager/IGS-Employee-Manager
```

Crie seu ambiente Virtual

```bash
virtualenv venv
```

Ative o ambiente criado

```bash
source venv/bin/activate
```

Instale as dependencias do projeto

```bash
pip install -r requirements.txt 
```

Migre

```bash
python manage.py makemigrations
python manage.py migrations
```

Crie o usuario de administração

```bash
python manage.py createsuperuser
```

Inicie o serviço

```bash
python manage.py runserver 4040
```

Acesse o serviço

```bash
http://localhost:4040/
```
## Rodando os testes

Para rodar os testes, rode o seguinte comando

```sh
curl -H "Content-Type: application/javascript" http://localhost:4040/employee/
```
#### Saida:

```sh
[
  {
    "id": 1,
    "name": "Will",
    "email": "lima@will.com",
    "department": "TI"
  },
  {
    "id": 2,
    "name": "Marcela",
    "email": "marcela@will.com",
    "department": "RH"
  }
]
```



```sh
curl -H "Content-Type: application/javascript" http://localhost:4040/depa
rtment/
```

#### Saida:

```sh
[
  {
    "id": 1,
    "name": "RH",
    "description": "Departamento pessoal"
  },
  {
    "id": 2,
    "name": "TI",
    "description": ""
  }
]
```