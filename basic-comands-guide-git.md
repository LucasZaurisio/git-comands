# GUIA DE COMANDOS BÁSICOS GIT

Este é um guia de comandos básicos que são mais utilizados caso você tenha o interesse em se aprofundar mais no assunto, recomendo acessar a <a href= "https://git-scm.com/doc">documentação do gitHub<a> lá voce terá mais detalhes sobre os comandos. Aqui te ofereço somente um resumo.

Iniciando um Repositório

* {% filename %}git init{% endfilename %} - na pasta onde vc quer o repositório a ser commitado (Cria repositório local)

* git add "nome do arquivo" ou "." - para colocar na area de stage(sob supervisão do git) sendo o ponto adiciona todos os arquivos

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

git remote add nome do repositório  "caminho do servidor"		     Para conectar um servidor externo ao seu código

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
			    



		
# calculatorJS
A simple calculator made with HTML, CSS and vanilla JS( without frameworks)