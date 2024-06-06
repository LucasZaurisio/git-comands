# GUIA DE COMANDOS BÁSICOS GIT

Eu elaborei esse arquivo com o intuito de ajudar pessoas encontrarem facilmente os comandos que são mais utilizados no dia a dia de um dev. Porr que muitas das vezes para quem está iniciando encontrar o que precisa na documentação do git, as vezes não é muito amigavel, então fiz um compilado rápido so meu entendimento sobre os comandos.

Este é um guia rápido de comandos básicos GIT, ou seja, os que são mais utilizados durante a rotina de um dev.

 Caso você não entenda algo por aqui, ou queira se aprofundar mais no assunto, recomendo acessar a <a href= "https://git-scm.com/doc">documentação do Git<a> lá voce terá mais detalhes sobre os comandos. Aqui te ofereço somente um resumo. Espero que ajude !

## Iniciando um Repositório local

* git init - na pasta onde vc quer o repositório a ser criado (Cria repositório local)

## fazendo a conexão do seu repositório local com o GitHub
> lembrando que para executar esse comando você já tem que ter um repositório criado no GitHub 

* git remote add "nome do repositório  "caminho do servidor (HTTP/SSH)"

## Colocando os Arquivos em Stage

* git add "nome do arquivo" ou "."

>para colocar arquivos na area de stage(sob supervisão do git).  "sendo o ponto adiciona todos os arquivos"

git status                                           para verificar como vão os os arquivos.

git -rm -- cached "nome do arquivo"                  para remove-lo da area de stage.

git commit -m "mensagem para citar as alteraçoes"    Para commitar o Arquivo!!!!!! NAO ESCREVA TEXTAO !!!!!!

git config --local user.name "Seu nome aqui"         Para definir/alterar seu nome

git config --local user.email "seu@email.aqui"	     Para definir/alterar seu e-mail


!!!!!caso apareça mutas informaçoes alem da tela no console apertar a tecla Q!!!!!!!


git log                                              Para Informações Sobre o commit

git log --oneline                                    Para informaçoes em uma linha(resumida)

git log -p                                           Para Informaçoes completas Commit

git log -n "n"				             aparece somente os "n" ultimos commits feitos


caso vc  queira que o git NAAAAAO monitore algum arquivo. Crie um arquivo chamado git ignore e adicione dentro dele os arquivos que vc quer que ele ignore
em caso de pastas colocar /nomedapasta que ele ignora toda a pasta

!!!NUNCA COMMITAR CODIGO NAO FUNCIONAL!!!

Commitar a cada funcionalidade inserida

git init --bare					                             Para Criar um Repositório PURO! só contém as  										     alterações dos arquivos



git remote -v								     visualizo meus repositórios

git push "nome do repositorio" "nome da branch"                              Envia dados para o servidor

git pull "nome do repositório" "nome da branch"				     Pega os dados do servidor e manda para a branch selecionada

git fetch "nome do repositório"/"nome da branch"			     Pega os dados do repositório remoto e manda para a 									     branch, só que ele não faz as mudanças diretamente 									     no código, voce precisa promeiro dar um git diff

git push -u(sempre manda pro origin) "nome do repositório"                   Envia dados para o servidor

git branch								     verifica quais branchs estão criadas e fala em qual está

git branch "nome da branch"                                                  Cria uma branch

git checkout "nome da branch"						     Troca entre as branchs

git checkout -b "nome da branch"					     Cria uma branch e ja troca para ela

git merge "nome da branch onde quer mesclar"				     junta os trabalhos e gera um merge commit na branch atual

git rebase "nome da branch que quer mesclar"				     aplica os commits de uma branch na branch atual

git branch -m "novo nome da branch"                                       Renomeia o nome da branch(a branch tem que estar em head)


!!!!!!!em qualquer caso entrar no editor VIM digitar ":x" !!!!!!!!!!!!!!!!
em casos de conflitos de alterações dar pull no arquivo mais atual e atualizar ele!

Git Checkout tbm serve para navegar entre estados no codigo

git checkout -- "nome do arquivo"					     Desfaz as alteraçoes que não foram mandadas para o stage(DOCS SEM COMITAR)

git reset "HEAD (o estado em que vc fez pull)" "nome do arquivo"             Tira o arquivo da fase de stage(marcadas pra commit)

git revert "hash do commit pego no git log"                                  Desfaz um commit

git stash								     Salvar o seu trabalho sem fazer commit

git stash list								     Retorna a lista de seus trabalhos em stash

git stash apply "numero do stash"                                            aplica todas as alteraçoes do stash selecionado no seu codigo atual. mas não tira o trablaho feito do stash

git stash drop "numero do stash"                                             Apaga um trabalho salvo no stash

git stash pop							             é a junção do git apply + git drop	

PARA NAVEGAR ENTRE COMMITS ANTERIORES


git checkout "numero do hash pego no git log --oneline"                     Navega para qualquer commit feito anteriormente por vc
(Lembrando que o git ja identifica o hash pelos 7 primeiros numeros/letras. 
e quando esse arquivo é aberto. ele é desanexado do restante do projeto. 
vc é livre para fazer alteraçoes e testes sem mexer no projeto todo ou em proximos commits)

!!!!!PARA FAZER QUALQUER ALTERAÇÃO NESSE COMMIT NAVEGADO, EU PRECISO CRIAR UM NOVO BRANCH E FAZER COMMIT, SENAO O CODIGO FICA DESANEXADO DA LINHA PRINCIPAL"

git checkout master 							    vc volta para o estado real de onde está seu projeto

git diff "hash do commit numero 1".."hash do commit numero 2"		    voce vê a diferença entre os 2 commits selecionados 

git diff								    voce visualiza tudo que voce alterou na head em que vc está usando


!!TAG marca um checkpoint no codigo (como nos jogos de videogame) e oficializa uma versão!!

git tag -a "nomeclatura da versão" -m "mensagem desejada"		    gera um marco na sua aplicação

git tag 								    mostra todas as versões ja feitas
			    