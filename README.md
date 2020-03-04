# Manual de Criação e Manuseamento de um Projeto Git

## INTRODUÇÃO

> Como criar e manusear um projeto Git


## I- ALGUMAS FUNÇÕES

== Exibir Interface Gráfica ==
> gitk


== Verificar ___usuário configurado___ ==
> git config user.name 

> git config user.email


== Caso ___não tenha config___, realizar os comandos as seguir: ==
> git config --global user.name "__<nome_do_usuario>__"

> git config --global user.email "__<email_do_usuario>__"


## II- O PROJETO GIT E SEUS ARQUIVOS

== ___Inicializar___ um projeto git ==
> git init 


== ___Verificar___ os status do projeto ==
> git status


== Criar o arquivo ___.gitignore___ ==
> touch .gitignore


== Criar o arquivo ___README___ ==
> touch README.md


== Para ___"trackar" (adicionar)___ os arquivos ==
> git add .gitignore //nome do arquivo que você quer adicionar ao git

ou

> git add .		 //adiciona todas as modificações ao git

ou

> git add -A	 //adiciona e acompanha todas as modificações trackeadas e não trackeadas ao git

ou 

> git add *.__<extenção do arquivo>__


## III. COMMIT

== ___Aplicar___ o commit ==
> git commit -m "início do projeto"	 	// mensagem de identificação da alteração (SEMPRE COLOCÁ-LO ENTRE ASPAS)


== ___Ajustar/Reescrever/Reverter___ o Commit Local Antes do Push  ==
> git commit --amend

ou

> git commit --amend -m "__<texto_do_commit>__"

> (Para mais informações acesse o __link 5__ e __link 6__)


== Voltar para um Commit Específico Localmente ==
> git reset --hard __<hash_do_commit>__   //elimina os commits posteriores ao hash selecionado


== Voltar para um Commit Especifico Remotamente ==
> git reset --hard __<hash_do_commit>__

> git add .

> git commit -m "__<texto_do_commit>__"

> git push -f origin __<nome_da_branch>__   //-f (força as substituições)


== Editar Commit no Repositório ==
> git rebase -i HEAD~n    //n = quantidade de commit que deseja rever a partir do último head


== Deletar o histórico de Commit no Repositório do Github ==

+------------ __AVISO__ ------------+

| Esta ação removerá completamente  |

| seus antigos commits. Não podendo |

| ser possível recuperá-los.        |

+-----------------------------------+

> git checkout --orphan temp_branch   //Criando uma nova branch que não é mostrada pelo comando 'git branch'

> git add -A    //Add todos os arquivos na nova branch criada

> git commit -am "o primeiro commit"    //add uma nova commit

> git branch -D master    //deleta a branch master do seu repositório git

> git branch -m master    //após deletar a master, vamos renomear a nova branch para __master__

> git push -f origin master   //após todas essas mudanças, forçe um push com suas novas mudanças e pronto!


## IV. REPOSITÓRIO

== ___Verificar___ qual repositório está configurado ==
> git remote -v


== ___Conectar___ ao repositório na nuvem ==
> git remote add origin https://github.com/bahamunt/MyGit.git	 // colocar o link do repositório


== ___Verificar___ mudanças no destino ==
> git fetch origin __<destino>__


== ___Baixar___ as mudanças no destino ==
> git pull origin __<destino>__


== ___Visualizar___ todos os commits ==
> git log


== ___Clonar Projeto___ do Repositório ==
> git clone --branch __<nome_da_branch> <url_da_branch>__

ou 

> git clone __<url_da_branch>__ 	//nesse caso ele sempre pega da master


== ___Visualizar___ Branchs existentes ==
> git branch -a


== __Trocar__ de Branch Local ==
> git checkout __<nome_da_branch>__


== __Criar__ Nova Branch Local ==
> git checkout -b <nome_da_branch>


== __Deletar__ Branch Local ==
> git branch -d __<nome_da_branch>__

ou

> git branch -D __<nome_da_branch>__

== __Subir__ a Nova Branch Local para a Nova Branch no Repositório (Remoto) ==
> git push origin __<nome_da_branch>__


== __Deletar__ a Branch Remoto ==
> git push --delete origin __<nome_da_branch>__

ou

> git push origin :__<nome_da_branch>__


== Comparar Branch ==
> git diff __<branch_raiz> <branch_destino>__


== Comparar Diferenças Dentro de uma Branch ==
> git diff


## V. HEAD

== Visualizar o HEAD __COMPLETO__ de um Commit ==
> git rev-parse HEAD


== Visualizar o HEAD __CURTO__ de um Commit ==
> git rev-parse --short HEAD


## VI. TAGS

== Criação de __Tags__ (Rotulação) ==
> git tag __<nome_da_tag> <hash_do_commit>__ 	//hash_do_commit = número_do_commit

> git push --tags origin __<nome_da_branch>__


== Deletar __Tag Local__ ==
> git tag -d __<nome_da_tag>__


== Deletar __Tag no Repositorio__ ==
> git push origin :__<nome_da_tag>__


## VII. BRANCHS

== Merge de Branchs ==
> git merge __<nome_da_branch>__ //OBS: é necessário estar na Branch que você quer receber as modificações e aplicar esse comando sempre chamando a branch que deseja juntar


== Rebase de Branchs ==
> git rebase __<nome_da_branch>__


== Correção de Conflito para __Tag__ e __Branch__ com o Mesmo Nome ==

PARA DELETAR _Tag_ :

> git push origin :refs/tags/__<nome_da_tag>__


PARA DELETAR _Branch_ :

> git push origin :refs/heads/__<nome_da_branch>__


## VII. ALTERAÇÕES

== Remover as Alterações Locais ==
> git stash							//coloca no cache os arquivos

> git checkout --__<nome_do_arquivo>__ 	//remove o arquivo escolhido


== Remover __PERMANENTEMENTE__ as Alterações Locais  ==
> git reset --hard 					//remove todas as alterações


## VIII. ALTERAÇÕES

== Corrigir o Arquivo ___.gitignore___ ==
> git rm -r --cached .

> git add .

> git commit -m "__<texto_do_commit>__"

> git push origin __<nome_da_branch>__

## IX. ALTERANDO O REPOSITÓRIO REMOTO(origin)

> git remote rm origin

> git remote add origin __<novo_repositório_a_ser_apontado.git>__

#================================================================#

> ___NOTA___

> rebase -i = ações interativas do rabase;

> Os comandos de refaturação aceitos:

> p(pick) = usar o commit atual para não alterar;

> r(reword) = usa o commit e edita a mensagem;

> e(edit) = usa o commit, mas não faz o amend;

> s(squash) = usa o commit, mas mescla com o commit anterior

> f(fixup) = semelhante ao _squash_, mas descarta o log de commit


> ___EXEMPLO 1___ 

> git rebase -i HEAD~2

> //Aparecerá os dois últimos commits no modo de edição:

> pick e499d89 Delete CNAME

> pick 0c39034 Better README

> //Escolhe qual commit deseja alterar:

> reword 0c39034 __<novo_texto>__

> //A cada alteração salve e feche a lista de commits.

> //Atualize o repositório com o comando:

> git push --force

#================================================================#





#=========================================================#

> ___NOTA___

> A diferença entre __MERGE__ e __REBASE__ é que enqunato

> o __MERGE__ mescla os projetos e cria um commit, o

> __REBASE__ coloca as modificações após o último commit

> e cria um commit no final.

> (Para mais informações acesse o _link 3_ dos EXTRAS)

#--------------------------------------------------------#

> __RESUMO DE COMO USAR OS COMANDOS COMMIT E PUSH__

> Estar na branch desejada

> git status //mostra o que foi alterado

> git add . //adiciona as alterações

> git commit -m " xxxxx "

> git push origin __<nome_da_branch>__

#========================================================#

## EXTRAS: Links para Mais Informações
>1: https://github.com/joshnh/Git-Commands

>2: https://rogerdudler.github.io/git-guide/index.pt_BR.html

>3: https://medium.com/datadriveninvestor/git-rebase-vs-merge-cc5199edd77c

>4: https://brorlandi.github.io/git-desfazendo-commits

>5: https://help.github.com/en/articles/changing-a-commit-message

>6: https://www.atlassian.com/git/tutorials/rewriting-history

>7: https://tecadmin.net/delete-commit-history-in-github/

## VERSÃO 1.6 (POR __Thales Samuel__ & __Marcelo Nidal__)
