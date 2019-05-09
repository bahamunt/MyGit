# Manual de Criação e Manuseamento de um Projeto Git

## INTRODUÇÃO

> Como criar e manusear um projeto Git

## FUNÇÕES

== Verificar usuario configurado ==
> git config user.name 

> git config user.email


== Caso não tenha config, realizar os comandos as seguir: ==
> git config --global user.name "<nome_do_usuario>"

> git config --global user.email "<email_do_usuario>"


== Inicializar um projeto git ==
> git init 


== Criar o arquivo .gitignore ==
> touch .gitignore


== Criar o arquivo README ==
> touch README.md


== Verificar os status do projeto ==
> git status


== Para "trackar" (adicionar) os arquivos ==
> git add .gitignore //nome do arquivo que vc quer adicionar ao git

ou

> git add .		 //adiciona todas as modificacoes ao git

ou

> git add -A	 //adiciona e acompanha todas as modificacoes trackeadas e não trackeadas ao git

ou 

> git add *.[extencao do arquivo]


== Aplicar o commit ==
> git commit -m "inicio do projeto"	 	// mensagem de identificacao da alteracao (SEMPRE COLOCA-LO ENTRE ASPAS)


== Verificar qual repositorio ele esta configurado ==
> git remote -v


== Conectar ao repositorio na nuvem ==
> git remote add origin https://github.com/bahamunt/MyGit.git	 // colocar o link do repositorio


== Verificar mudancas no destino ==
> git fetch origin <destino>


== Baixar as mudancas no destino ==
> git pull origin <destino>


== Visualizar todos os commits ==
> git log


== Clonar Projeto do Repositorio ==
> git clone --branch <nome_da_branch> <url_da_branch>

ou 

> git clone --branch <url_da_branch> 	//nesse caso ele sempre pega da master


== Trocar de Branch Local ==
> git checkout <nome_da_branch>


== Criar Nova Branch Local ==
> git checkout -b <nome_da_branch>


== Deletar Branch Local ==
> git branch -d <nome_da_branch>

ou

> git branch -D <nome_da_branch>


== Subir a Nova Branch Local para a Nova Branch no Repositorio (Remoto) ==
> git push origin <nome_da_branch>


== Deletar a Branch Remoto ==
> git push --delete origin <nome_da_branch>

ou

> git push origin :<nome_da_branch>


== Comparar Branch ==
> git diff <branch_raiz> <branch_destino>


== Comparar Diferencas Dentro de uma Branch ==
> git diff


== Criacao de Tags (Rotulacao) ==
> git tag <nome_da_tag> <hash_do_commit> 	//numero_do_commit

> git push --tags origin <nome_da_branch>


== Remover as Alteracoes Locais ==
> git stash							//coloca no cache os arquivos

> git checkout --<nome_do_arquivo> 	//remove o arquivo escolhido


== Remover PERMANENTEMENTE as Alteracoes Locais  ==
> git reset --hard 					//remove todas as alteracoes


== Voltar para um Commit Especifico Localmente ==
> git reset --hard <hash_do_commit>	//elimina os commits posteriores ao hash selecionado


== Voltar para um Commit Especifico Remotamente ==
> git reset --hard <hash_do_commit>

> git add .

> git commit -m "<texto_do_commit>"

> git push -f origin <nome_da_branch> // -f força as substituicoes


== Corrigir o Arquivo '.gitignore' ==
> git rm -r --cached .

> git add .

> git commit -m "<texto_do_commit>"

> git push origin <nome_da_branch>


== Interface Gráfica Padrão ==
> gitk



## EXTRA: Links para Mais Informacoes
> https://github.com/joshnh/Git-Commands

> https://rogerdudler.github.io/git-guide/index.pt_BR.html


## VERSÃO 1.0 (POR BAHAMUNT)
