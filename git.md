- **criar um repositório:**

```sh
$ echo "# nomedorepo" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git remote add origin https://github.com/mlpbraga/nomedorepo.git
$ git push -u origin master
```
No git trabalhamos em `branchs`, que são ramificações da arvore de desenvolvimento do nosso projeto.

- **criar um branch novo**
```sh
$ git checkout -b nome-do-branch
```

- **listar todos os branchs**
```sh
$ git branch
```

- **trocar de branch**
```sh
$ git checkout nome-do-branch
```

- **adicionar alterações feitas no seu local**
```sh
$ git add .              #adiciona todas as alterações, ou
$ git add nomedoarquivo  #adicionar o arquivo especificado
```
esse comando não envia suas alterações pro remoto

- **commitar alterações feitas no seu local**
```sh
$ git commit -m "mensagem de comit"
```

- **enviar suas alterações para o remoto (onde todos os colaboradores podem ver)**
```sh
$ git push origin nome-do-branch
```

- **atualizar seu repositório para ver alterações commitadas por outras pessoas**
````sh
$ git fetch
$ git pull origin nome-do-branch
