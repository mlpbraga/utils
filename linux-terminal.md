# Comandos úteis de linux

**Observaçes**
* Diretórios correspondem ao que você conhece como as pastas do seu computador
* Os caminhos de diretórios são separados pos `/` e são representados da esquerda para a direita simulando o repositório mais externo e o mais interno respectivamente
#
**Comandos simples**
* **exibir o manual de como utilizar um comando**: `man comando`
* **limpar a tela do terminal**: `clear`
* **exibir o caminho do diretório atual**: `pwd`
* **entrar em um diretório**: `cd caminho-do-diretorio`
  * **voltar para o diretório anterior**: `cd ..`
  * **ir para o diretório ~/**: `cd`
* **listar todos o conteúdo do diretório atual**: `ls`
  * **listar conteúdo do diretório atual com seus tamanhos, datas de modificação e tipos**: `ls -l`
  * **listar conteúdo do diretório atual incluindo os arquivos invisíveis**: `ls -la` ou `ls -l -a`
* **criar um diretório**: `mkdir nome-novo-diretorio`
* **excluir um diretório**: `rmdir nome-do-diretorio` *obs:* não podemos apagar um diretório que possui subdiretórios ou arquivos com esse comando
* **excluir um diretório com todo o seu conteúdo**: `rm - r diretorio/`
* **excluir um arquivo**: `rm arquivo.txt`
* **exibir uma mensagem no terminal**: 
  * exibir cada palavra como argumento: `echo Ola`
  * exibir uma string: `echo "Olá"`
* **contar o número de palavras, caracteres e linhas que um arquivo possui**: `wc -w nome.txt`, `wc -c nome.txt`, `wc -l nome.txt`
* **escrever um texto em um arquivo**:
  * **sobrescrever conteúdo atual do arquivo**: `echo "Texto de teste" > teste.txt`
  * **adicionar texto ao final do arquivo**: `echo "mais um texto" >> teste.txt`
* **exibir no terminal conteúdo de um arquivo**: `cat teste.txt`
  * **exibir o conteúdo do arquivo mostrando as linhas do arquivo**: `cat -n texte.txt`
* **copiar o conteúdo do arquivo X para o arquivo Y**: `cp x.txt y.txt`
  * **copiar um diretório com todo o seu conteuo**: `cp -r diretorio-x diretorio-y`
* **mover o conteudo de um arquivo X para o arquivo Y**: `mv x.txt y.txt` *obs:* isso apaga o arquivo de onde o conteúdo foi movido
* **exibir o nome do usuário linux que está logado**: `whoami`
* **compactar um arquivo:** `zip -r arquivo.zip caminho-a-ser-zipado/`
* **listar quais arquivos e diretórios foram compactados**: `unzip -l arquivo.zip`
* **exibir as 10 primeiras linhas de um aquivo**: `head arquivo.txt`
  * **exibir as n primeiras linhas de um arquivo**: `head -n n arquivo.txt`
* **exibir as dez ultimas linhas de um arquivo**: `tail arquivo.txt`
  * **exibir as n ultimas linhas de um arquivo**: `tail -n n arquivo.txt`
* **abrir o arquivo e navegar por ele com as setas do teclado**: `less arquivo.txt` fechamos o less com o comando `q` do teclado
#
**Uso do VIM**

Se você digitar `vim arquivo.txt` no terminal e não existir nenhum arquivo com o nome `arquivo.txt` no diretório onde você está, o vi criará um arquivo com esse nome. Caso esse arquivo já exista, o vi irá apenas abrir esse arquivo com todo o seu conteúdo.

Quando você abre o arquivo, o vim permite que você navege por ele usando as setas do teclado, esse é o modo de navegação.

Para poder incluir ou deletar conteúdo do arquivo dentro do vim, você deve presionar a tecla `i`, uma vez pressionada você estára livre para alterar o arquivo. Para sair desse modo, basta apertar `esc` para voltar para o modo de navegação.

Para salvar quaisquer alterações feitas no arquivo, você deve digitar `:w` e para sair do vi, você pode digitar o comando `:q`. Para salvar e sair, use `:wq` e para sair sem salvar, use o comando `:q!`.

Para buscar por termos no vim, presione o botão `/` e digite sua busca, se tiverem mais resultados alm do que você encontrou, você pdoe navegar por eles apertando `n`.

# 
**Gerenciamento de processos**

* **listar quais processos estão em execução**: 
    * **exibir os processos de terminal**: `ps`
    * **exibir todos os processos da máquina**: `ps -e`
    * **exibir todos os processos da máquina com informaçes** `ps -ef`
    * **exibir informações do processo específico**: `ps -ef | grep firefox`
    * **exibir processos de maneira gráfica**: `pstree`
* **solicitar o fechamento de um processo por id**: `kill ID` ex: `kill 1221`
    * **força a finalização do processo**: `kill -9 ID`
    * **sinaliza que o programa deve ser finalizado apenas depois de realizar algumas tarefas**: `kill -TERM ID` *Obs: quando não indicamos nenhum sinal para o comando kill, é o sinal TERM que é executado por padrão*
    * **matar todos os processos de um mesmo programa**: `killall nomedoprograma`
* **lista a situação dos processos, do processador e da memória**: `top` *Obs: A lista de processos está organizada pelo uso da CPU, e se atualiza dependendo desse uso.*
    * **mostrar apenas os processos de um determinado usuário**: `top -u usuario`
    * **acompanhar as informações de um processo específico**: `top -p ID`
    * *Obs: Por padrão, o top atualiza a tela com novas informações sobre os processos a cada 3 segundos. Para alterar esse tempo basta pressionar d enquanto estiver rodando o top, inserir o valor desejado e pressionar a tecla Enter: `Change delay from 3,0 to 1`*
* **visualizar processos que estão parados**: `jobs`
* **enviar processo para ser executado em background**: `bg ID` 
* **inicializar o processo já em background**: `nomedoprocesso &`
* **trazer processo para ser executado em foreground**: `fg ID`

#
**Instalar programas**

* **ver as versões atualizadas dos programas que estão disponíveis para instalação**: sudo apt-get update
* **instalar programas**: `sudo apt-get install programa`
* **remover programas**: `sudo apt-get remove programa`
* **instalar programa usando dpkg**: `sudo dpkg -i pacote.deb`
* **desinstalar programa usando dpkg**: `sudo dpkg -r pacote`

*Obs: duas formas de instalar e desinstalar programas no Linux:

1. Via apt: quando o programa já está disponibilizado na central do Sistema Operacional Linux.

2. Via dpkg: quando baixamos pelo navegador da internet um pacote .deb do programa.*

#
**Criando um programa**

1. Criar um arquivo gedit em background: `gedit dorme &`
2. Inserir o conteúdo:
```sh
echo "Vou dormir"
sleep 5
echo "Terminei de dormir"
```
3. Executar o programa: `sh dorme`

#
**Permissões**

Os arquivos no Linux podem ter permissões para leitura (r), escrita (w) e execução (x). Essas permissões são distribuídas para o dono do arquivo, ao grupo de usuários e também para outros usuários. Os diretórios (d) sofrem das mesmas regras.

* **adicionar permissão de execução para o arquivo dorme**: `chmod +x dorme`
* **localiza onde está o programa**: `locate firefox`
* **exibe onde os programas estão instalados**: `wich firefox`
* **atualizar senha do usuário linux**: `passwd`
* **adicionar novo usuário**: `adduser novo`
* **logar no usuário novo**: `su novo`
* **tirar permissões dos arquivos do novo para os demais usuários**: `chmod o-rx novo` *obs: Neste caso, o comando chmod é seguindo de alguns operadores, que são: o para others, ou seja, outros usuários, o - indica uma remoção de permissão, o r e x indicam permissões de leitura e execução. Se quiséssemos tirar permissões do próprio usuário, seria: u-rx e para o grupo seria: g-rx.*

Para executarmos o programa dorme como todos os outros, fazemos:

```sh
sudo mv dorme /usr/bin
```
ou 

```sh
PATH=$PATH:caminho-do-arquivo
```
