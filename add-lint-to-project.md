## Adicionando eslint em um projeto JavaScript

1. Na pasta do projeto, adicionar a dependência do eslint:
```sh
$ npm i eslint -D
```
2. Adicionar o `lint` no `package.json` da seguinte forma:
```json
\\package.json

{
  ...
  "scripts": {
    ...
    "lint": "eslint ./src --fix",
    ...
  }
  ...
}
```

3. Inicializar o lint no projeto rodando:
```
$ npm run lint -- --init
```

Deve ser gerado um arquivo `.eslintrc` com as suas configurações de lint. O conteúdo dele deve ser similar a esse:
```json
\\ .eslintrc.json

{
    "env": {
        "browser": true,
        "commonjs": true,
        "es6": true
    },
    "extends": "eslint:recommended",
    "globals": {
        "Atomics": "readonly",
        "SharedArrayBuffer": "readonly"
    },
    "parserOptions": {
        "ecmaVersion": 2018
    },
    "rules": {
    }
}
```

O comando para rodar o lint no seu projeto é:
```sh
$ npm run lint
```
