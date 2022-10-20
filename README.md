# 🖥️ Corrigindo o Código - Ignite - Rocketseat

Essa aplicação realiza o CRUD (Create, Read, Update, Delete) de repositórios de projetos. Além disso, é possível dar likes em repositórios cadastrados, aumentando a quantidade de likes em 1 a cada vez que a rota é chamada.

Esse é o desafio 03 do primeiro módulo da trilha de NodeJS do Ignite da Rocketseat. O desafio está disponível no seguinte link:

https://www.notion.so/Desafio-03-Corrigindo-o-c-digo-c15c8a2e212846039a367cc7b763c6dd

## 🧑‍💻 Tecnologias utilizadas

- [NodeJS](https://nodejs.org/en/)
- [Express](https://expressjs.com/pt-br/)
- [Insomnia](https://insomnia.rest/)

## 📌 Index

- [Instalando as ferramentas](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#-instalando-as-ferramentas)
  - [Instalando o NodeJS](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#instalando-o-nodejs)
  - [Instalando o Yarn](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#instalando-o-yarn)
  - [Instalando o Insomnia](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#instalando-o-insomnia)
- [Executando o Projeto](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#-executando-o-projeto)
- [Inicializando o Projeto](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#-inicializando-o-projeto)
- [API](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#%EF%B8%8F-api)
  - [Requisitos da Aplicação](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#requisitos-da-aplica%C3%A7%C3%A3o)
  - [Rotas](https://github.com/GabrielFerreira98/ignite-conceitos-do-nodejs#rotas)

## 🧰 Instalando as Ferramentas 

Os passos desse tópico foram realizados no sistema operacional do Windows.

### Instalando o NodeJS

É possível fazer o download pelo [Site oficial do NodeJS](https://nodejs.org/en/download/)

Após o download, abra o Windos PowerShell no modo administrador e digite a seguinte linha de código para ver se o Node foi instalado corretamente:

```
node -v
```

### Instalando o Yarn

O Yarn é o gerenciador de pacotes que será utilizado para baixar todas as dependências e executar o projeto. Caso você deseje fazer com o NPM, pode pular esta etapa.
Há duas possibilidades de baixar o Yarn

1. Pelo site oficial do [Yarn](https://yarnpkg.com/)
2. Rodar o seguinte comando no terminal:
```
npm install -g yarn
```

### Instalando o Insomnia

Pode ser baixado pelo próprio site do [Insomnia](https://insomnia.rest/download)

## 🚀 Executando o projeto

Faça o clone do projeto no Powershell 

```
#faça o clone do projeto
git clone 

#entre na pasta baixada
cd ignite-conceitos-do-nodejs
```

### Abrindo o projeto

Abra o projeto utilizando alguma IDE. Esse projeto foi feito utilizando o [VSCode](https://code.visualstudio.com/)

### Instalando as dependências

Instale as dependências do projeto utilizando a seguinte linha de comando:

```
yarn install
```

## 🏃 Inicializando o projeto

Rode a linha de comando

```
yarn run dev
```

Mantenha o terminal rodando para utilizar o projeto

## 🖥️ API

### Requisitos da Aplicação

#### Requisitos de likes

1. Deve ser possível dar um like em um repositório
2. Não deve ser possível dar um like em um repositório não existente

#### Requisitos de repositórios

1. Deve ser possível criar um novo repositório
2. Deve ser possível listar todos os projetos
3. Deve ser possível atualizar um repositório
4. Não deve ser possível atualizar um repositório não existente
5. Não deve ser possível atualizar os likes de um repositório manualmente
6. Deve ser possível deletar um repositório
7. Não deve ser possível deletar um repositório não existente

A URL base a ser usada como exemplo será uma variável base_url. Considere que ela armazene o valor http://localhost:3333.

### Rotas

POST - base_url/repositories

#### Descrição

Essa rota realiza o cadastro de um repositório a partir de um title, url e techs

#### Body

```
{
  title: 'Some title',
  url: 'https://github.com/GabrielFerreira98/ignite-corrigindo-o-codigo/edit/main/README.md',
  techs: 'NodeJS'
}
```

#### Resposta

```
{
    id: uuid(),
    title: 'Some title',
    url: 'https://github.com/GabrielFerreira98/ignite-corrigindo-o-codigo/edit/main/README.md' ,
    techs: 'NodeJS',
    likes: 0
  }
```

Status code: ```201```

GET - base_url/repositories

#### Descrição

Essa rota retorna todos os repositórios cadastrados

PUT - base_url/repositories/:id

#### Descrição

Essa rota atualiza um repositório com um id

#### Body

```
{
  title: 'Some title',
  url: 'https://github.com/GabrielFerreira98/ignite-corrigindo-o-codigo/edit/main/README.md',
  techs: 'NodeJS'
}
```

#### Resposta

```
{
    id: uuid(),
    title: 'Some title',
    url: 'https://github.com/GabrielFerreira98/ignite-corrigindo-o-codigo/edit/main/README.md' ,
    techs: 'NodeJS',
    likes: 0
  }
```

Status code: ```201```

Possível erro

O repositório não existe: ```{error: "Repository not found}``` - Status code: ```404```


DELETE - base_url/repositories/:id

#### Descrição

Essa rota deleta um repositório a partir de um id

Possível erro

O repositório não existe: ```{error: "Repository not found}``` - Status code: ```404```

POST - base_url/repositories/:id/likes

Essa rota aumenta em 1 o número de likes de um repositório a partir de um id

Params

```
id = request.params
```

Possíveis erros

O repositório não existe: ```{error: "Repository not found}``` - Status code: ```404```

