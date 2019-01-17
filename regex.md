# Regex

`.` -> qualquer caractere

`?` -> zero ou uma vez

`*` -> zero, uma ou mais vezes

`{}` -> servem para definir uma quan dade de caracteres específicas que é desejado
encontrar

`{n}` -> exatamente n vezes

`{n,}` -> no mínimo n vezes

`{n,m}` -> no mínimo n vezes, no máximo m vezes

`[A-Z]` -> significa de A até Z, sempre maiúscula

`[a-z]` -> significa de a até z, sempre minúscula

`[A-Za-z]` -> significa A-Z ou a-z

`[abc]` -> significa a, b ou c

`\d` -> um dígito, atalho pra [0-9]

`[.-]` -> ponto ou hífen (pode ser u lizado para quaisquer caracteres) 

`[.-]*` -> ponto ou hífen zero, uma ou mais vezes

`[.-]{1}` -> ponto ou hífen uma vez

`[.-]?` -> ponto ou hífen zero ou uma vez

#

Para procurar um ponto, traço ou um asterisco de fato, precisamos usar `\.` , `-` ou `\*`
 
* Existem âncoras predefinidas que selecionam uma posição dentro do alvo.
* \b é uma âncora que seleciona um word boundary, isso é o início ou fim da
palavra.
* ^ é uma âncora que seleciona o início da string alvo.
* $ é uma âncora que seleciona o fim do alvo.

#

**Todos os quan fiers são gananciosos por padrão.** Isso significa que eles automáticamente selecionam o máximo de caracteres. Lembrando que temos os seguintes quan fiers:
* ? (zero ou um caractere)
* \+ (um ou mais caracteres)
* \* (zero ou mais caracteres)
* {n,m} (min n, max m caracteres)

Podemos utilizar um `?` logo após o quantifier, deixando-o preguiçoso.

#

**Exemplo de CRF:**

```
\d{3}\.\d{3}\.\d{3}\-\d{2}

ou

\d{3}[.-]?\d{3}[.-]?\d{3}[.-]?\d{2}
```

**Exemplo do CNPJ:**
```
\d{2}\.\d{3}\.\d{3}\/\d{4}\-\d{2}
```

**Exemplo de IP:**
```
\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}
```

**Exemplo de Número de Telefone:**
```
\(\d{2}\) \d{4}-\d{4}
```

**Exemplo de Datas:**

21 de Maio de 1993

```
[0123]?\d\s+de\s+[A-Z][a-zç]{1,8}\s+de\s+[12]\d{3}
```

**Exemplo de Horários:**

19h32min16s

```
\d{2}h\d{2}min\d{2}s
```

#

**Exercícios:**

Ao trabalharmos com datas, é bem comum visualizá-las em diversos formatos, como, por exemplo, 20 de maio de 2015 ou 20 maio 2015. Para o nosso sistema, a preposição de não faz tanto sen do quanto para o usuário e, portanto, podemos ignorá-la. Sabemos que podemos pedir ao Regex Engine para que não devolva nenhum grupo específico através de non-capturing groups.

O que queremos então é pedir ao Regex Engine para que não devolva o grupo formado pelo de e por um whitespace ( \s ). Qual das opções abaixo faz um uso correto dos non-
capturing groups?

Resposta correta: `(?:de\s+)?`

Na Alura existe um filtro de permissões para habilitar alguns recursos para usuários da Alura ou da Caelum. A sua tarefa é criar a regex que verifica o email desses usuários e extrair o nome do usuário.

O email deve ter um @ e terminar com caelum.com.br ou alura.com.br. O nome do usuário (tudo antes do @ ) tem apenas letras minúsculas, pode ter um número no final e tem de 5 a 15 caracteres.

Por exemplo:

super.mario@caelum.com.br extrai super.mario

donkey.kong@alura.com.br extrai donkey.kong

bowser1@alura.com.br extrai bowser1

Mais uma dica, para definir dentro de um grupo que queremos um OU outro usamos o
caractere | (pipe). Por exemplo, selecionando alfa OU beta , escrevemos
(alfa|beta)

Segue uma possível regex:
([a-z.]{4,14}[a-z\d])@(?:caelum.com.br|alura.com.br)

