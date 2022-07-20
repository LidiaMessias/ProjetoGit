Esse arquivo está presente na maioria dos projetos.
Leia-me antes de fazer qualquer coisa no projeto. É mais ou menos isso que ele é, um arquivo de instruções.

Iniciar um repositório Git vazio => Comando: git init (Tem que estar dentro da pasta do projeto que queremos programar/alterar)

Adicionar arquivos ao repositório Git => git add Readme.md (nome do arquivo e sua extensão)

Verificar o status dos arquivos do repositório Git => git status (verifica se eles já foram comitados ou se estão em standing)

Para comitar um arquivo para o repositório git => git commit -m "Primeiro commit" (Entre aspas colocamos: "Texto qualquer a que se refere este commit, pode ser qualquer informação tipo: Alteração do menu de eventos, por exemplo")

O Git está mudado a nomenclatura da branch principal que atualmente é (master) para (main). É só uma nomenclatura diferente. Existem empresas que já adotaram essa nova nomenclatura, assim como outras que ainda estão utilizando a nomenclatura padrão. É importante se informar a respeito com as equipes de trabalho para saber qual forma está sendo utilizada.
Para alterar o nome da branch principal digitamos => git branch -M "main" 

Github é uma plataforma para hospedar todos os nossos códigos. Dessa forma podemos acessar em qualquer computador, através da nossa conta do GitHub, todos os códigos que estão armazenados nele e puxar para o computador.

Depois de criar um novo repositório no Github clicando no botão verde (New Repository), vamos linká-lo ao repositório do nosso projeto que está no computador. Para isso vamos digitar no gitbash => git remote add origin https://github.com/LidiaMessias/ProjetoGit.git (esse é o endereço do repositório que criamos no github).
Com esse comando estamos falando para o Git fazer a conexão do nosso repositório local com o repositório do GitHub.

Com o git já conectado com o GitHub só falta o comando para ele enviar o que já temos no nosso computador para o repositório do GitHub. O comando é => git push -u origin master (master é o nome da branch principal).
Com esse comando ele pede para autenticarmos o acesso ao Github para certificar que somos nós mesmos que estamos enviando o código (para não correr o risco de outras pessoas alterarem nosso código), e assim que fizermos a autenticação, é só cliar no botão de atualizar a página e ele já carregou nosso projeto.

Depois de feito mais alterações no nosso projeto, criado novos arquivos e etc, temos que usar git add novamente para enviar os arquivos para a área de standing. Podemos digitar o nome do arquivo que foi modificado ou simplesmente digitar . (ponto) que ele vai mandar todos os arquivos do projeto. O comando é => git add . E em seguida temos que commitar essas alterações e inclusões => git commit -m "Nome das nossas alterações ou inclusões, o que quisermos escrever".

Depois do commit feito temos que jogar esse commit para o GitHub, então digitamos: git push origin master (Lembrando que a primeira vez que fazemos a conexão do repositório com o GitHub usamos o -u no comando, as demais vezes não precisa usá-lo mais). Com esse comando o git atualiza nosso projeto no GitHub.

Branch => Branch é uma ramificação do repositório principal do nosso projeto (master). A branch é utilizada para criarmos ou alterarmos alguma coisa sem jogar/mexer na branch master. É muito utilizada para que façamos os testes primeiro para saber se está tudo funcionando, antes de jogar essas alterações/criações para a branch principal do projeto.

Para criar uma branch => git checkout -b "novo-botao" (Entre parênteses o nome da nova branch, pode ser qualquer nome)
Com esse comando, além do git criar uma nova branch (novo-botao) ele vai sair da branch master e já entrar nessa branch criada.

Em seguida, fazemos as alterações/criações que queremos e salvamos. E depois, temos que fazer o mesmo processo para commitar essas alterações/criações feitas e jogar lá no nosso repositório remoto (GitHub).
git add .
git commit -m "Criação do arquivo novo botão" 
git push origin novo-botao (Repare que aqui estamos colocando o nome da nova branch, então o git vai enviar para o GitHub a nova branch e tudo o que a gente fez nela)

Para retornar ou alterar de uma branch para outra digitamos:
git checkout master (master é o nome da branch que queremos acessar, então ele sai da branch atual e vai para a master)

Para mesclarmos o que foi feito em uma branch secundária (novo-botao) com o que está na branch principal (master) precisamos estar dentro da branch master e em seguida digitamos:
git merge novo-botao (novo-botao é o nome da branch que queremos juntar à principal)

E para jogarmos essa mesclagem para o Github usamos o mesmo comando que joga as alterações/criações para o repositório remoto (Github):
git push origin master
Os arquivos que antes só apareciam na branch secundária, lá no GitHub agora já aparecem na branch master, uma vez que fizemos a mesclagem dos 2 arquivos. (merge)

Agora vamos ver como puxar todo o meu projeto que está no GitHub para o meu computador. Isso serve para quando usamos mais de um computador para fazermos nosso projeto, por exemplo, um aqui em casa e outro na casa da minha mãe. Posso deixar ele sempre atualizado para que eu acesse ele em qualquer lugar que eu estiver.

Lá no GitHub entramos no nosso perfil, clicamos em repositórios, selecionamos o repositório que queremos acessar e vai aparecer um botão verde escrito CODE. Clicamos nele e copiamos o link que aparece com o botão de cópia que fica ao lado do nome do link.
Em seguida criamos uma nova pasta no computador onde queremos clonar o nosso projeto que está no Github. Criei a pasta com o nome de GitTutorial
Abrimos essa pasta e clicamos com o botão direito, e selecionamos Git Bash Here. Ele vai abrir um terminal gitbash e nele vamos digitar:
git clone https://github.com/rafaballerini/GitTutorial.git (git clone <link que copiamos lá do Github>)

Ele vai criar nessa pasta uma cópia do projeto que estava no GitHub. 
Quando quisermos pegar alguma atualização de um projeto do GitHub que a gente já tenha feito o clone, e que tenha novas alterações/criações:
Temos que entrar na pasta do projeto, para esse exemplo, no gitbash vamos digitar:
cd gittutorial (gittutorial é o nome da pasta do projeto)
Dentro da pasta digitamos:
git pull

Se o projeto já estiver aberto no VS Code, feche ele e abra de novo. Pronto, as alterações já foram atualizadas na nossa pasta do computador.

Podemos clonar também repositórios de outras pessoas através do link que elas nos passarem. Nesse caso aqui, se eu quiser que o repositório GitTutorial da Rafa Ballerini seja copiado para meus repositórios no GitHub devemos:
Clicar no botão FORK que está no canto superior direito da página do repositório dessa pessoa
Na próxima página que abrir siga as instruções da tela e clique em CREATE A FORK.
Pronto, o repositório foi copiado para o seu GitHub.

Por último vamos aprender como utilizar o Pull Request
Quando fazemos um fork de um projeto de alguém, clonamos no nosso computador e fazemos algumas alterações/criações em cima desse projeto dessa pessoa, a gente pode questionar a pessoa se ela quer adicionar essas nossas alterações no projeto dela.
Para isso a gente faz um Pull Request para essa pessoa, uma solicitação para ela fazer um pull da alteração que fizemos. Daí a pessoa aceita ou não. 
Depois que fizermos as alterações/criações nesse projeto e atualizarmos ele no nosso Github, a gente vai clicar no botão Contribute que fica na linha debaixo do botão Code e vamos clicar no botão:
OPEN PULL REQUEST 
Ele vai abrir uma nova tela e nos informar se estamos Able to merge. Se sim, clicamos no botão CREATE PULL REQUEST
Sempre que fizermos um pull request vai abrir uma tela para escrevermos comentários para o desenvolvedor do projeto sobre todas as alterações que fizemos. Escrevemos tudo que quisermos informar para essa pessoa. Digitado o comentário clicamos no botão CREATE PULL REQUEST que fica lobo abaixo da caixa de comentários.
Feito isso esperamos a resposta da pessoa.

Como aceitar um PULL REQUEST
No nosso perfil, no repositório de um projeto nosso, na linha de menu tem a opção de Pull requests. Se existir algum pull request que nos foi solicitado ele aparecerá alí.
Quando clicamos nessa opção (Pull Request) vai abrir uma outra tela com as solicitações de pull request que fizeram para nós e com os comentários do que se trata. Se estivermos de acordo e for do nosso interesse, clicamos no botão:
MERGE PULL REQUEST e ele atualiza o projeto no nosso repositório remoto com as alterações feitas por essa pessoa. Se quisermos trazer essas alterações para o repositório do nosso projeto no NOSSO COMPUTADOR, seguimos os mesmos passos já descritos um pouco acima, que são para atualizar nosso repositório com alterações que estão no repositório remoto (GitHub):
Temos que entrar na pasta do projeto dentro do gitbash;
cd <nome da pasta do projeto>
E dentro da pasta digitamos:
git pull

Pronto, tudo atualizado.











