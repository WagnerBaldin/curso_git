Adicionei o link do curso em C


https://github.com/bytegarage/c-programming-bootcamp


# curso_git
Curso de Git e Github com arquivos exemplos e configurações

**Comandos iniciais git**

**Limpar a tela no gitbash**

clear
crtl+l

**Visualizando a versão do git instalada**

git --version
git -v

**Criando as variáveis globais de nome e email**

git config --global user.name "Nome Sobrenome"
gir config --global user.email "xyz@gmail.com"

**Visualizando as variáveis globais de nome e email, local ou global**

git config user.name
git config --get user.name

git config user.email
git config --get user.email

**Exibe todas as configurações do Git, incluindo tanto configurações locais (específicas ao repositório) quanto globais (usuário)**

git config --list

**Exibe todas as configurações globais, ou seja, aquelas que se aplicam a todos os repositórios do usuário**

git config --global --list

**Criando uma pasta**
mkdir nome_da_pasta

**Acessando a pasta**
cd nome_da_pasta

**Saindo da pasta**
cd ..

**Vendo o conteúdo da pasta**
ls

**Criando um Arquivo novo através do Git**
touch teste.txt

**Inserindo uma linha no arquivo com >**
echo "primeira linha inserida" > teste.txt

**Vendo o conteúdo do arquivo criado**
cat.teste.txt

**Modificando o texto no arquivo com >**
echo "mudando o texto" > teste.txt

**Inserindo uma linha a mais com >>**
echo "inserindo outra linha" >> teste.txt

**Modificando o texto de uma linha específica**
sed -i '2s/.*/novo texto segunda linha/' teste.txt

**Apagando o conteúdo do arquivo**
> teste.txt
ou
truncate -s 0 teste.txt
ou
echo "" > teste.txt

**Excluindo um arquivo**
rm teste.txt

**Excluindo TODOS arquivo**
rm *
rm *.*
rm -rf *

**Remover a pasta e TODO seu conteúdo**
rm -rf nome_da_pasta


**Criando um repositório**

git init

**Apagando um repositório -- NÃO PODE SER DESFEITO**

rm -rf .git

Para excluir o arquivo `teste.txt` no Git Bash, siga estes passos:

1. **Remova o arquivo do diretório** (sistema de arquivos):

rm teste.txt

2. **Remova o arquivo do repositório Git** 
(para refletir a exclusão no próximo commit):

git rm teste.txt


3. **Adicione a exclusão ao stage**:

git add teste.txt

4. **Confirme a mudança**:

git commit -m "Remover teste.txt"

5. **Envie a mudança para o repositório remoto** (se aplicável):

git push

---------------------------

**Criando o Primeiro commit**

git commit -m "criando primeiro commit"

**Vendo o Log de coomits feitos**

git log

**Vendo o commite da "cabeça", o primeiro**

commit bd42d5a38cd518744c83f9 (HEAD -> main)

**Entendendo sobre as Branchs**

A Branch Main é uma versão específica do sistema
Como ver a Branch que eu estou agora

git branch

* main -> mostra a branch que eu estou

**Criando uma BRANCH**

git branch nomeDaNovaBranch

**Trocando de Branch**

git switch nomeDaNovaBranch

  main
* minhaNovaBranch

**renomear a branch atual**

git branch -m novoNome

**Renomeando o último commit**

git commit --amend -m "Nova mensagem do commit"

**Criando uma Branch de Emergência - de fix**

pode ser feito criando a nova branch e depois mudando
mas também dá pra criar e já mudar pra ela

git switch -c branch-fix

**Deletando uma Branch criada por engano**

OBS: use -D se ainda não foi mergeado
     use -d se já foi mergeado

git branch -D branch-fix

**Fazendo um Merge na Main com a branch com correções**

voltar para a Branch principal e chamar as
correções da branch que teve alguma alteração

git switch main

git merge teste

Agora git traz o que foi corrigido e alterado 
para a bench principal

**Deletando uma Branch de correção após um Merge**

git branch -d teste

CAso tenha alguma alteração na branch de teste
é preciso fazer um merge novamente

**Git Ignore**

.gitignore

Pode ser usando para fazer algumas anotações
arquivo que deve ser ignorado pelo Git
Define arquivos que serão ignorados no repositório
Ele vai ignorar pastas e arquivos que estejam
listados no arquivo ignore

Arquivos de configurações podem ter alguns
arquivos que devem ser ignorados nos commits pra
não darem problema
Alguns arquivos devem ficar somente na máquina

Adicionar cada nome de arquivo ou pasta no .gitignore
e depois esses arquivos serão ignorados ficando 
somente no repositório local

**Corrigindo mensagens do commit**

para ver o log de commits:

git log (com muito mais informações)

git log --oneline (reumido)

Esse último, mostra as linhas das mensagens
ficando mais fácil de ver quais foram
os commits feitos

Esse altera a mensagem do último commit (HEAD)

git commit --amend -m "colocando a frase nova"

**Voltando para outro commit**

**git revert**

retornando para o último commit
o comando --no-edit mantém a mensagem anterior
git revert HEAD --no-edit

**git reset**

eu quero voltar o processo anterior

**git stash**

esse comando volta os arquivos para situações
que ainda não foram commitadas, basicamente

git stash

**git diff** muito pouco usado!

por exemplo, escolhendo um commit e o HEAD
ele vai mostrar as alterações entre esses
dois commits que foram feitos

git diff a00545e HEAD

**Abortando merge com conflito**

Caso na main tenha uma alteração de uma 3ª branch
e na nova branch as alterações conflitarem
com essa branch main que está diferente
Pode abortar o conflito com o comando:

git merge --abort

**Agora Entra o GitHub**
