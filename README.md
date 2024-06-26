# GUIA DE COMANDOS BÁSICOS GIT

Eu elaborei esse arquivo com o intuito de ajudar pessoas encontrarem facilmente os comandos que são mais utilizados na rotina de um dev. Por que muitas das vezes para quem está iniciando encontrar o que precisa na documentação do git, as vezes não é muito amigavel, então fiz um compilado rápido so meu entendimento sobre os comandos.

Este é um guia rápido de comandos básicos GIT, ou seja, os que são mais utilizados no dia a dia de um dev.

 Caso você não entenda algo por aqui, ou queira se aprofundar mais no assunto, recomendo acessar a <a href= "https://git-scm.com/doc">documentação do Git. </a> Lá voce terá mais detalhes sobre os comandos. Aqui te ofereço somente um resumo. Espero que ajude !

## Lista de comandos

* ```git init``` - Inicia repositório local na pasta onde você quer o repositório local seja criado.

* ```git remote add "nome do repositório" "caminho do servidor (HTTP/SSH)"``` - conecta repositório local ao GitHub
> Pré requisito para executar esse comando, é ter o seu repositório ja criado no GitHub.

* ```git add "nome do arquivo" ou "."``` - Coloca arquivos selecionados em stage. O ```.``` adiciona todos os arquivos modificados em stage.

* ```git status``` - Verifica os arquivos que estão na area de stage.
* ```git -rm -- cached "nome do arquivo"```- Remove os arquivos da area de stage
* ```git commit -m "mensagem para citar as alteraçoes"``` - Faz o commit dos arquivos em stage na mensagem escreva o que foi modificado <b>NAO ESCREVA TEXTAO !</b>
* ```git config --local user.name "Seu nome aqui" ``` - Para definir/alterar seu nome de usuário
* ```git config --local user.email "seu@email.aqui"``` - Para definir/alterar seu e-mail de usuário
> Os dois ultimos comandos são essenciais principalmente para quando se está trabalhando em grupo. Ex: Encontrar quem fez o commit.

* ```git log``` - Obtem-se informações sobre os commits ja feitos, Ex: hash do commits, dia, hora, mensagem.
* ```git log --oneline``` -  Para informaçoes  de log resumidas.
* ```git log -p``` - Para Informaçoes completas dos Commits.
* ```git log -n "5"``` - Mostra somente os "5" ultimos commits feitos
* ```git init --bare``` - cria um Repositório PURO! só contém as alterações dos arquivos feitos por push.
* ```git remote -v``` - Visualizo meus repositórios 
* ```git push "nome do repositorio" "nome da branch"``` - Após o commit esse é o comando que envia os dados do seu repositório local para o GitHub.
* ```git pull "nome do repositório" "nome da branch"```- Pega os dados do GitHub e manda para a branch selecionada

* ```git fetch "nome do repositório"/"nome da branch"``` - Pega os dados do GitHub e manda para a branch selecionada, só que as alterações precisam de revisão no comando ```git diff```para depois ser feito um ```git pull```

* ```git push -u(sempre manda pro origin) "nome do repositório"``` - Envia commits feitos para o GitHub

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
			    
!!!!!caso apareça mutas informaçoes alem da tela no console apertar a tecla Q!!!!!!!
caso vc  queira que o git NAAAAAO monitore algum arquivo. Crie um arquivo chamado git ignore e adicione dentro dele os arquivos que vc quer que ele ignore
em caso de pastas colocar /nomedapasta que ele ignora toda a pasta

!!!NUNCA COMMITAR CODIGO NAO FUNCIONAL!!!

Commitar a cada funcionalidade inserida
