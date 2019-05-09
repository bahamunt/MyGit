# Manual de Criacao e Manuseamento do Git

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
> git add -A //adiciona e acompanha todas as modificacoes trackeadas e não trackeadas ao git
ou 
> git add *.<extencao do arquivo>

== Aplicar o commit ==
> git commit -m "inicio do projeto" // mensagem de identificacao da alteracao (SEMPRE COLOCA-LO ENTRE ASPAS)
ou
> git commit -a "alteracao no README" // primeiro ele olha a arvore de arquivos, notifica as alteracoes e já realiza as acoes 'git.add' e 'git rm' automaticamente

== Verificar qual repositorio ele esta configurado ==
> git remote -v

== Conectar ao repositorio na nuvem ==
> git remote add origin https://github.com/bahamunt/MyGit.git // colocar o link do repositorio

== Verificar mudancas no destino ==
> git fetch


