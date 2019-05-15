# Manual de Criação e Manuseamento de um Projeto Git

## INTRODUÇÃO

> Como criar e manusear um projeto Git

## FUNÇÕES

== Verificar usuário configurado ==
> git config user.name 

> git config user.email


== Caso não tenha config, realizar os comandos as seguir: ==
> git config --global user.name "__<nome_do_usuario>__"

> git config --global user.email "__<email_do_usuario>__"


== Inicializar um projeto git ==
> git init 


== Criar o arquivo .gitignore ==
> touch .gitignore


== Criar o arquivo README ==
> touch README.md


== Verificar os status do projeto ==
> git status


== Para "trackar" (adicionar) os arquivos ==
> git add .gitignore //nome do arquivo que você quer adicionar ao git

ou

> git add .		 //adiciona todas as modificações ao git

ou

> git add -A	 //adiciona e acompanha todas as modificações trackeadas e não trackeadas ao git

ou 

> git add *.__<extenção do arquivo>__


== Aplicar o commit ==
> git commit -m "início do projeto"	 	// mensagem de identificação da alteração (SEMPRE COLOCÁ-LO ENTRE ASPAS)


== Ajustar/Reescrever/Reverter o Commit Local Antes do Push  ==
> git commit --amend

ou

> git commit --amend -m "__<texto_do_commit>__"

> (Para mais informações acesse o __link 5__ e __link 6__)


== Verificar qual repositório ele está configurado ==
> git remote -v


== Conectar ao repositório na nuvem ==
> git remote add origin https://github.com/bahamunt/MyGit.git	 // colocar o link do repositório


== ___Verificar___ mudanças no destino ==
> git fetch origin __<destino>__


== ___Baixar___ as mudanças no destino ==
> git pull origin __<destino>__


== Visualizar todos os commits ==
> git log


== Clonar Projeto do Repositório ==
> git clone --branch __<nome_da_branch> <url_da_branch>__

ou 

> git clone --branch __<url_da_branch>__ 	//nesse caso ele sempre pega da master


== _Trocar_ de Branch Local ==
> git checkout __<nome_da_branch>__


== _Criar_ Nova Branch Local ==
> git checkout -b <nome_da_branch>


== _Deletar_ Branch Local ==
> git branch -d __<nome_da_branch>__

ou

> git branch -D __<nome_da_branch>__

== Subir a Nova Branch Local para a Nova Branch no Repositório (Remoto) ==
> git push origin __<nome_da_branch>__


== Deletar a Branch Remoto ==
> git push --delete origin __<nome_da_branch>__

ou

> git push origin :__<nome_da_branch>__


== Comparar Branch ==
> git diff __<branch_raiz> <branch_destino>__


== Comparar Diferenças Dentro de uma Branch ==
> git diff


== Visualizar o HEAD __COMPLETO__ de um Commit ==
> git rev-parse HEAD


== Visualizar o HEAD __CURTO__ de um Commit ==
> git rev-parse --short HEAD


== Criação de Tags (Rotulação) ==
> git tag __<nome_da_tag> <hash_do_commit>__ 	//hash_do_commit = número_do_commit

> git push --tags origin __<nome_da_branch>__


== Remover as Alterações Locais ==
> git stash							//coloca no cache os arquivos

> git checkout --__<nome_do_arquivo>__ 	//remove o arquivo escolhido


== Remover __PERMANENTEMENTE__ as Alterações Locais  ==
> git reset --hard 					//remove todas as alterações


== Voltar para um Commit Específico Localmente ==
> git reset --hard __<hash_do_commit>__	//elimina os commits posteriores ao hash selecionado


== Voltar para um Commit Especifico Remotamente ==
> git reset --hard __<hash_do_commit>__

> git add .

> git commit -m "__<texto_do_commit>__"

> git push -f origin __<nome_da_branch>__ //-f (força as substituições)


== Corrigir o Arquivo ___.gitignore___ ==
> git rm -r --cached .

> git add .

> git commit -m "__<texto_do_commit>__"

> git push origin __<nome_da_branch>__


== Merge de Branchs ==
> git merge __<nome_da_branch>__ //OBS: é necessário estar na Branch que você quer receber as modificações e aplicar esse comando sempre chamando a branch que deseja juntar


== Rebase de Branchs ==
> git rebase __<nome_da_branch>__


#====================================================#

> ___NOTA___

> A diferença entre __MERGE__ e __REBASE__ é que enqunato

> o __MERGE__ mescla os projetos e cria um commit, o

> __REBASE__ coloca as modificações após o último commit

> e cria um commit no final.

> (Para mais informações acesse o _link 3_ dos EXTRAS)

#====================================================#


== Exibir Interface Gráfica ==
> gitk


## EXTRAS: Links para Mais Informações
>1: https://github.com/joshnh/Git-Commands

>2: https://rogerdudler.github.io/git-guide/index.pt_BR.html

>3: https://medium.com/datadriveninvestor/git-rebase-vs-merge-cc5199edd77c

>4: https://brorlandi.github.io/git-desfazendo-commits

>5: https://help.github.com/en/articles/changing-a-commit-message

>6: https://www.atlassian.com/git/tutorials/rewriting-history

## VERSÃO 1.3 (POR __BAHAMUNT__ & __Marcelo Nidal__)
