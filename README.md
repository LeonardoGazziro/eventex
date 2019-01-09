# EVENTEX

Sistema de Eventos encomendado pela morena

[![Build Status](https://travis-ci.org/LeonardoGazziro/eventex.svg?branch=master)](https://travis-ci.org/LeonardoGazziro/eventex)

## Como desenvolver?

1. Clone o repositório.
2. Crie um virtualenv  com python 3.7
3. Ative o virtualenv.
3. Instale as depêndencias.
5. Configure a instância com o .env
6. Execute os testes

```console
git clone git@github.com:LeonardoGazziro/eventex.git wttd\Django
cd wttd\Django
python -m venv .wttd
.\.wttd\scripts\activate
pip install -r requirements-dev.txt
cp contrib/env-sample .env
python manage.py test
```

## Como fazer o deploy?
1. Crie uma instância no heroku.
2. Envie as configurações para o heroku.
3. Defina uma SECRET_KEY segura para instância.
4. Defina DEBUG=False.
5. Configure o serviço de email.
6. Envie o código para o heroku.

```console
heroku create minhainstancia
heroku config:push
heroku config:set SECRET_KEY=`python contrib\secret_gen.py`
heroku config:set DEBUG=False
# configuro o email
git push heroku master --force
```