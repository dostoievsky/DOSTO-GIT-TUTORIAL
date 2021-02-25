## DOSTO-GIT-TUTORIAL

# AS DESCRIÇÕES AQUI REALIZADAS FORAM FEITAS TENDO COMO BASE E FONTE O CURSO 
# GOSTACK BOOTCAMP DA ROCKETSEAT.

# EXISTEM INTERFACES GRAFICAS PARA TRABALHAR COM GIT, ALÉM DOS COMANDOS AQUI 
# DESCRITOS, PORÉM NÃO TRATAREI DESSES RECURSOS, CASO TENHA INTERESSE NESTAS, 
# BASTA UMA PESQUISA NA WEB PARA SABER QUAIS SÃO, VERIFIQUE TAMBÉM O GitLens.

O GitHub é um sistema de repositorios de codigos muito utilizado por desenvolvedores.
A sua importancia é enorme, pois além de auxiliar a mantermos um repositorio global 
de codigo, também permite que empresas analisem a produção de um desenvolvedor através
dos repositorios ali disponibilizados.

Uma de suas poderosas ferramentas é a capacidade de manter-se um controle de versão de
varios desenvolvedores, resolvendo conflitos de forma dinamica e simples através de seus
Pulls requests, além de manter backups de alterações que podem ser restaurados quando 
necessário.

Então basicamente, através dos commits, criamos versionamentos do codigo num repositorio,
que é de extrema valia para o desenvolvimento de um projeto.


## PORQUE USAR GIT
Mesmo que você esteja desenvolvendo sozinho, essa ferramenta ainda é de muita valia.
Quem nunca trabalhou num projeto através de N locais diferentes, com diferentes máquinas?
E sem usar GIT, foi necessario um HD externo, ou então um serviço de armazenamento online
como GDrive, Dropbox e etc.

Porém, a medida que o desenvolvimento se complica, e dependendo da linguagem utilizada,
somos obrigados a nos valer de gerenciadores de pacotes, e ainda confiar que tais serviços
de armazenamento lidem com todas as bibliotecas e pacotes adicionais utilizadas além das 
disponiveis no compilador.

Utilizando o Git, o gerenciamento do codigo se simplifica, e convenhamos, torna-se muito 
mais pratico que a utilização dos serviços de armazenamento, além de muito mais intuitivos!


## COMO AS RAMIFICAÇÕES FUNCIONAM?
Ramificações são as Branchs do GitHub, através delas, podemos alterar diferentes aréas 
de nosso código sem que estas sofram conflitos. Caso uma feature esteja em desenvolvimento
e em algum momento desse processo seja necessário voltar a uma parte já implementada por 
conta de um problema ou melhoria, podemos particionar ambas as features através das Branchs.

## NÃO TRABALHE NO MASTER/MAIN BRANCH
Trabalhe sempre através das ramificações, e só adicione-a ao master/main branch quando souber 
que a determinada funcionalidade é realmente essencial ao projeto e está bem implementada.


## COMO INSTALAR O GIT
Usuarios de MAC já vem com o git instalado, bastanto instalar o Xcode Command Linetools para
utilizar.

Usuarios windows podem instalar através do site:
https://git-scm.com/

Usuarios LINUX bastam seguir os comandos listados no mesmo site para a respectiva plataforma:
https://git-scm.com/download/linux


## PRIMEIRO CONTATO COM O GIT
(ESSA SESSÃO TRATARÁ APENAS DO GIT INTERNO, NÃO DO GITHUB, GITLAB OU GITHUB, 
ESTAS SERÃO DESCRITAS MAIS A FRENTE NESSE TUTORIAL)

Após instalação, escolha um repositorio para anexar ao git e abra seu executor de
comandos na pasta do projeto. 
Agora execute o comando:


# git init
Esse comando significa que será iniciado um repositorio git no determinado diretorio,
criando a primeira ramificação, denominada por padrão master.


## .gitignore
A pasta .gitignore é um recurso utilizado para que desterminadas pastas ou arquivos 
não sejam anexadas ao sistema git. É muito util, pois podem existir modulos que não 
são interessantes ao git.

Em JavaScript por exemplo, temos a pasta node_modules, que anexa certas bibliotecas
utilizadas por um padrão de compilação. Caso o projeto seja desenvolvido em JS, esta
pasta pode e deve ser ignorada ao anexamento Git.

Para tal, basta criarmos um arquivo '.gitignore' na nossa pasta de desenvolvimento,
e adicionar o nome das pastas/arquivos que devem ser ignorados no nosso anexamento.


## git commit
O git commit permite criar pontos na historia do Git, para versionamento e
historico de mudança.

Antes de utilizar-lo, porem, devemos escolher quais pastas ou arquivos serão 
adicionadas ao commit. Para tal, devemos utilizar o comando:
# git add <arquivo1> <arquivo2> <arquivoN> <pasta1> <pasta2> <pastaN>

Caso queira adicionar todas as pastas e arquivos, além das que já estão sinalizadas
em nosso .gitignore, basta utilizar o comando:
# git add .

Para termos acesso aos arquivos e pastas esperando um commit, utilizamos o comando:
# git status
Este comando exibirá o Branch sendo utilizado, os commits já realizados nele, e também
os diretorios selecionados para commit.

Caso queiramos remover um determinado diretorio que havia sido adicionado durante o 
git add, por motivo de erro, mudanças, ou o que for, podemos utilizar o comando:
# git rm --cached <arquivo1> <arquivo2> <arquivoN>
Ou então, para todos os arquivos:
# git rm --cached .

Finalmente, para realizarmos o commit de fato, executamos o seguinte comando:
# git commit -m "mensagem_titulo_do_commit"
Para a mensagem titulo do commit existem varios padrões, como por exemplo o GitFlow
e muitas outras disponibilizadas na Web. Você também pode criar o seu proprio padrão,
mas tenha em mente que esta mensagem é de suma importancia, pois através dela que
você se guiará pelo historico de mudanças de seu codigo.

Geralmente essa mensagem segue o seguinte padrão:
# "<PREFIXO> <DESCRIÇÃO>"

O prefixo deve sinalizar o tipo de alteração sendo realizada em seu codigo, esta pode 
ser uma alteração de concerto "fix", introdução de novas funcionalidades "feature", 
expansão de codigo ou simplesmente algo que não é necessariamente um fix, ou feature: 
"chore"

Podemos, também, verificar o historico de commits com o camando:
# git log


## UTILIZANDO O GITHUB
Para associarmos os nossos gits internos a um serviço online, como o GitHub, devemos 
criar um repositorio online na plataforma.
O proprio GitHub disponibilizará uma sequencia de comandos para a anexar o nosso 
repositorio local ao repositorio online.
Os comandos git init, git add e git commit, já foram descritos acimas, agora, 
trataremos dos comandos que não utilizamos ainda, assim como suas devidas explicações:


# git remote add nome <url_repositorio>
Esse comando simboliza que estamos sinalizando ao nosso repositorio local "remote" 
para adicionar "add" um vinculo sinalizado por um "nome" (por padrão, origin) 
a um repositorio online "url_repositorio".
No lugar de add, podemos realizar diversas funções, como por exemplo, a de deletar 
um vinculo já estabelecido.


Agora podemos enviar nossos commits (pontos no historico) ao repositorio vinculado, 
para tal, utilizamos o comando:
# git push -u nome branch
Esse comando significa que estamos enviando "push", ao branch padrão através de 
upstream "-u" repositorio "nome" na ramificação "branch", como o Hub informa:
# git push -u origin main
Em caso de sucesso, passamos a ver no nosso repositorio online os arquivos 
enviados em commits, assim como o historico de versões criado através dos commits.

Após esse primeiro push, caso queiramos continuar trabalhando com o branch em 
questão, basta que os proximos push sejam executados apenas como:
# git push

## COMO SEI EM QUE REPOSITORIO ESTOU?
Caso o repositorio tenha outro nome além de origim, é possivel descobri-lo 
através do comando:
# git remote -v 

## CRIANDO NOVAS RAMIFICAÇÕES
Como já descrito anteriomente, criamos ramificações "branchs" quando queremos 
fazer alterações no codigo sem comprometer o restante de uma estrutura já estabelecida.
Para tal utilizamos o comando:
# git checkout -b nomebranch
Ao ser executado, checkout garante que nosso terminal já acessse o 
branch "nomebranch" criado "-b".
Assim, os novos commits e pulls, não refletirão noutro branch previamente criado, 
o que garantirá que o codigo nele publicado não sofra alterações antes da devida 
hora, e também permitindo que multiplos desenvolvedores trabalhem simultaneamente 
no codigo sem conflito de alterações.
A partir de então, qualquer git add, push e desmasiados comandos, se relacionará 
apenas a devida ramificação em questão.

## NAVEGANDO ATRAVÉS DE RAMIFICAÇÕES
Vizualisando as Branchs num repositorio:
# git co

Basta utilizar o comando para ir até um branch:
# git checkout nomebranch

## UNINDO RAMIFICAÇÕES
Para trazer o codigo no main/master a um branch, ou entre branchs, basta acessar 
a branch que receberá as informações e usar o comando:
# git merge nome_da_branch_que_se_unira_a_branch_atual

# NÃO UTILIZE O MERGE PARA UNIR UM BRANCH AO MAIN/MASTER, PARA ISSO, 
# UTILIZE AS PULL REQUESTS DESCRITAS ABAIXO

Quando uma branch já está bem implementada, ela pode se unir a outras branchs 
para a complitude do sistema em desenvolvimento para tal contamos com os 
seguintes recursos:
# git push nome branch
Dentro de nosso repotorio a ser anexado, utilizamos este comando para criar um 
PULL REQUEST, ou seja, uma solicitação de novo codigo a ser anexado ao main branch.
Agora, basta ao desenvolvedor acessar a pagina do repositorio e descrever as 
mudanças realizadas na Branch, para que outros desenvolvedores no repositorio em 
questão avaliem e permitam a união dos ramos.

Para outro desenvolvedor realizar essa revisão, este deve ser selecionado como 
revisor na pagina do repositorio. Assim que este aprovar o codigo, poderá clicar 
em merge, para unir as branchs.

Os recursos não se limitam a isso, o revisor pode fazer comentarios, assim como 
requisitar mudanças antes que o codigo seja devidamente anexado. 

Caso o codigo precise ser removido, a plataforma ainda oferece a funcionalidade 
de reverter um determinado merge.

Tudo isso é fornecido pela plataforma online do GitHub.

Vale lembrar que o metodo da Pull Request não tem intenção de testar o codigo, 
apenas de revisa-lo, é recomendado que as Pull Request sejam testadas 
previamente de maneira unitaria pelos desenvolvedores.

# É uma boa pratica deletar uma branch quando está é finalmente anexada ao main, 
# o GitHub fornece também a possibilidade de restaurar uma branch removida, 
# caso necessario.

# CASO EXISTAM CONFLITOS, O PROPRIO GITHUB INFORMARÁ, E TAMBÉM PERMITIRÁ QUE OS 
# DESENVOLVEDORES RESOLVAM O CONFLITO INFORMADO. QUANDO O CONFLITO FOR RESOLVIDO, 
# BASTA FAZER UM NOVO PULL REQUEST PARA AVALIAÇÃO.


## COPIANDO UM REPOSITORIO GIT PARA A SUA MÁQUINA
Caso queiramos baixar um repositorio git publico, ou cujo tenhamos acesso 
privado a uma máquina, devemos usar o comando:
# git clone <url_repositorio>
O repositorio será baixado no respectivo diretorio em que a linha de comando foi 
executada. 




