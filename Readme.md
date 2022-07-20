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