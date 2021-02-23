# Trilha DevOps da 4Linux

<!-- Altere a Flag abaixo com sua URL do Travis -->
[![Build Status](https://travis-ci.com/gpohren/DevOpsLab-HelloWorld.svg?branch=master)](https://travis-ci.com/gpohren/DevOpsLab-HelloWorld)

## Aplicação criada para exemplificar o Ciclo de uma PipeLine DevOps


Para maiores informações acesse o [Site da 4Linux](https://www.4linux.com.br/cursos/devops)

## Ajustes

Estava com o seguinte problema no Travis CI:
```bash
No stash entries found.
API request failed.
Message: Invalid credentials provided.
Reference: 
failed to deploy
``` 
Alterado no arquivo .travis.yml

de:
```bash
  api_key:
    secure: $HEROKU_API_KEY
``` 
para:
```bash
  api_key: $HEROKU_API_KEY
```
Também estava ocorrendo problema no Heroku, pois a versão do Python não era compatível com a slack heroku-20.
```bash
By default, newly created Python apps use the python-3.6.13 runtime.
```
Instalado o Heroku CLI
```bash
$ curl https://cli-assets.heroku.com/install-ubuntu.sh | sh
``` 
Criando o Heroku-18
```bash
$ heroku create --stack heroku-18
``` 

Após isso, o deploy ocorreu com sucesso!

#### Referências

* [Failed to deploy (heroku): “API request failed. Message: Invalid credentials provided.”](https://travis-ci.community/t/failed-to-deploy-heroku-api-request-failed-message-invalid-credentials-provided/9988)

* [Heroku Python Support](https://devcenter.heroku.com/articles/python-support#supported-runtimes)

* [The Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

* [Using Heroku-18](https://devcenter.heroku.com/articles/heroku-18-stack#using-heroku-18)
