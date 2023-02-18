# Bem vindo ao Backend do pegavisao.org

Aqui estão algumas regras e boas práticas para termos um fluxo de branchs e changes dentro do projeto

## Fluxo de trabalho Git 
Atualmente o projeto tem como base o Trunk based development. Por isso temos poucas branchs envolvidas no fluxo:
- **main** - Branch protegida e é a que contém o código fonte que está rodando em ambiente produtivo
- **develop** - Branch que contém código fonte que está rodando em ambiente de teste. Assim que a homologação nesse ambiente é feita, é a partir dela que devemos ir para main
- **feature/nome-da-funcionalidade** - Branch criada a partir da main e é onde a pessoa desenvolvedora codifica seus códigos :)

![alt text](/docs/flow-pegavisao.png "Fluxo de trabalho do Pegavisao.org")


## Começando a contruibir
Quando for começar a codificar, você deve fazer o clone do projeto e criar sua branch a partir da Main, é ela que possui o código produtivo em pleno funcionamento. 

Alguns nomes para sua feature branchs são aceitos desde que sejam claros:
- **feat**/nome-da-minha-mudanca
- **feature**/nome-da-minha-mudanca
- **bugfix**/nome-da-correcao-bug
- **hotfix**/deu-ruim-em-producao

**feat** e **feature** são branchs que possuem adições de códigos/funcionalidades e pequenas melhorias.

**bufgix** é uma branch específica para correções de bugs em códigos/funcionalidades que já existem

**hotfix** é uma branch espefícia para correções urgentes que vão direto para ambiente protudivo afim de normalizar o funcionamento de aplicação 

Use sempre o kebab-case, este é o padrão adotado desde 18/02/2023.

## Merge Pull Request
Atualmente o projeto possui um template para ajudar na identificação das changes. Esse preenchimento é obrigatório apenas para PRs que tiverem a main como destino. 

Esse tipo de informação vai ajudar a todo mundo a identificar o que está indo para ambiente produtivo.

Caso você esteja apenas abrindo PR para develop, você pode ignorar.

## Referência

 - [Trunk based development](https://trunkbaseddevelopment.com/.)
 - [kebab-case](https://betterprogramming.pub/string-case-styles-camel-pascal-snake-and-kebab-case-981407998841)
