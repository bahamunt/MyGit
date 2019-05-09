# Tutorial de Criacao e Manuseamento do Git

## Introducao

> Como criar e manusear um projeto Git

## Tutorial

== Verificar usuario configurado ==
> git config user.name 
> git config user.email

== Caso não tenha config, realizar os comandos as seguir: ==
> git config --global user.name "thales thales"
> git config --global user.email "meuEmail@gmail.com"

== Inicializar um projeto git ==
> git init 

== Criar o arquivo .gitignore ==
> touch .gitignore

== Criar o arquivo README ==
> touch README.md

== Verificar os status do projeto ==
> git status

== Para "trackar" os arquivos ==
> git add .gitignore //nome do arquivo que vc quer adicionar ao git
ou
> git add . //adiciona todas as modificacoes ao git
ou
> git add -A //adiciona todas as modificacoes trackeadas e não trackeadas ao git
