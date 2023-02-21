
# Bem vindo ao Backend do pegavisao.org

  

Aqui estão algumas regras, boas práticas e instruções de como rodar o projeto localmente. Além de entender como funciona o versionamento, branchs e deploys

  

## Como rodar o projeto localmente

Instale as seguintes ferramentas:
- Python 3.8
- Docker
- IDE da sua preferência

Como rodar o projeto:
Com as ferramentas instaladas você deve criar 3 recursos antes de levantar a aplicação em ambiente local

Com docker, crie uma network: *docker network create nginx_nw*
```sh
C:\Users\luis\VisionBack>docker network create nginx_nw
```
 

Com docker, crie dois volumes: docker volume create nome_volume
```cmd
C:\Users\luis\VisionBack>docker volume create static
```

```cmd
C:\Users\luis\VisionBack>docker volume create docs
```

Feito os pré requisitos basta rodar o comando: docker compose up

```cmd
C:\Users\luis\favela_inc\VisionBack>docker compose up
```
```cmd
[+] Running 2/2
 - Container nginx             Created                                                                                                 0.1s 
 - Container visionback-web-1  Created                                                                                                 0.1s 
Attaching to nginx, visionback-web-1
nginx             | /docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
nginx             | /docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
nginx             | /docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
nginx             | 10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
nginx             | 10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
nginx             | /docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
nginx             | /docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
nginx             | /docker-entrypoint.sh: Configuration complete; ready for start up
visionback-web-1  | [2023-02-21 15:11:41 +0000] [1] [INFO] Starting gunicorn 20.1.0
visionback-web-1  | [2023-02-21 15:11:41 +0000] [1] [INFO] Listening at: http://0.0.0.0:5000 (1)
visionback-web-1  | [2023-02-21 15:11:41 +0000] [1] [INFO] Using worker: sync
visionback-web-1  | [2023-02-21 15:11:41 +0000] [7] [INFO] Booting worker with pid: 7
```
  

## Fluxo de trabalho Git

Atualmente o projeto tem como base o Trunk based development. Por isso temos poucas branchs envolvidas no fluxo:

-  **main** - Branch protegida e a que contém o código fonte do ambiente produtivo

-  **develop** - Branch que contém código fonte do ambiente de teste. Assim que a homologação nesse ambiente for feita, é a partir dela que devemos ir para main

-  **feature/nome-da-funcionalidade** - Branch criada a partir da main e é onde a pessoa desenvolvedora codifica suas alterações :)

  

![alt text](/docs/flow-pegavisao.png  "Fluxo de trabalho do Pegavisao.org")

  
  

## Começando a contruibir

Quando for começar a codificar, você deve fazer o clone do projeto e criar sua branch a partir da **main**, é ela que possui o código produtivo em pleno funcionamento.

  

Alguns nomes para sua feature branchs são aceitos desde que sejam claros e sigam os padrões abaixo:

-  **feat**/nome-da-minha-mudanca

-  **feature**/nome-da-minha-mudanca

-  **bugfix**/nome-da-correcao-bug

-  **hotfix**/deu-ruim-em-producao

  

**feat** e **feature** são branchs que possuem adições de códigos/funcionalidades, melhorias, refatorações, upgrade de librarys e etc.

  

**bufgix** é uma branch específica para correções de bugs em códigos/funcionalidades existentes.

  

**hotfix** é uma branch espefícia para correções urgentes que vão direto para ambiente produtivo afim de normalizar o funcionamento de aplicação o quanto antes.

  

Use sempre o kebab-case pois este é o padrão adotado desde 18/02/2023.

  

## Merge Pull Request

Atualmente o projeto possui um template para ajudar na identificação das changes. Esse preenchimento é obrigatório apenas para PRs que tiverem a **main** como destino.

  

Esse tipo de informação vai ajudar a todo mundo a identificar o que está indo para ambiente produtivo.

  

Caso você esteja apenas abrindo PR para develop, você pode ignorar.

  

## Referência

  

-  [Trunk based development](https://trunkbaseddevelopment.com/.)

-  [kebab-case](https://betterprogramming.pub/string-case-styles-camel-pascal-snake-and-kebab-case-981407998841)
