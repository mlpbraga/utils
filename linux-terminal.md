# Comandos úteis de linux

**Observaçes**
* Diretórios correspondem ao que você conhece como as pastas do seu computador
* Os caminhos de diretórios são separados pos `/` e são representados da esquerda para a direita simulando o repositório mais externo e o mais interno respectivamente
#
**Comandos**
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
