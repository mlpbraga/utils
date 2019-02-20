# Como imprimir coloridinho no terminal

*É pra funcionar no print de qualquer linguagem, basta você adicionar os códigos de COR no no inico e no final da string.*

```python
print("[COR]Quero imprimir isso aqui\33[0m")
```

Na sua função de imprimir, você só precisa substituir `[COR]` pelos códigos referentes a cor que você quer.

**Cor da fonte**
```python
# cor padrão
print("\33[39mQuero imprimir isso aqui\33[0m")

# preto
print("\33[30mQuero imprimir isso aqui\33[0m")

# vermelho
print("\33[31mQuero imprimir isso aqui\33[0m")

# verde
print("\33[32mQuero imprimir isso aqui\33[0m")

# amarelo
print("\33[33mQuero imprimir isso aqui\33[0m")

# azul
print("\33[34mQuero imprimir isso aqui\33[0m")

# magenta
print("\33[35mQuero imprimir isso aqui\33[0m")

# ciano
print("\33[36mQuero imprimir isso aqui\33[0m")

# cinza claro
print("\33[37mQuero imprimir isso aqui\33[0m")

# cinza escuro
print("\33[90mQuero imprimir isso aqui\33[0m")

# vermelho claro
print("\33[91mQuero imprimir isso aqui\33[0m")

# verde claro
print("\33[92mQuero imprimir isso aqui\33[0m")

# amarelo claro
print("\33[93mQuero imprimir isso aqui\33[0m")

# azul claro
print("\33[94mQuero imprimir isso aqui\33[0m")

# magenta claro
print("\33[95mQuero imprimir isso aqui\33[0m")

# ciano claro
print("\33[96mQuero imprimir isso aqui\33[0m")

# branco
print("\33[97mQuero imprimir isso aqui\33[0m")
```

**Cor de fundo**
```python
# cor padrão
print("\33[49mQuero imprimir isso aqui\33[0m")

# preto
print("\33[40mQuero imprimir isso aqui\33[0m")

# vermelho
print("\33[41mQuero imprimir isso aqui\33[0m")

# verde
print("\33[42mQuero imprimir isso aqui\33[0m")

# amarelo
print("\33[43mQuero imprimir isso aqui\33[0m")

# azul
print("\33[44mQuero imprimir isso aqui\33[0m")

# magenta
print("\33[45mQuero imprimir isso aqui\33[0m")

# ciano
print("\33[46mQuero imprimir isso aqui\33[0m")

# cinza claro
print("\33[47mQuero imprimir isso aqui\33[0m")

# cinza escuro
print("\33[100mQuero imprimir isso aqui\33[0m")

# vermelho claro
print("\33[101mQuero imprimir isso aqui\33[0m")

# verde claro
print("\33[102mQuero imprimir isso aqui\33[0m")

# amarelo claro
print("\33[103mQuero imprimir isso aqui\33[0m")

# azul claro
print("\33[104mQuero imprimir isso aqui\33[0m")

# magenta claro
print("\33[105mQuero imprimir isso aqui\33[0m")

# ciano claro
print("\33[106mQuero imprimir isso aqui\33[0m")

# branco
print("\33[107mQuero imprimir isso aqui\33[0m")
```

**Formatação**
```python
# negrito
print("\33[1mQuero imprimir isso aqui\33[0m")

# ofuscado
print("\33[2mQuero imprimir isso aqui\33[0m")

# sublinhado
print("\33[4mQuero imprimir isso aqui\33[0m")

# piscando
print("\33[5mQuero imprimir isso aqui\33[0m"
```


[Outros...](https://misc.flogisoft.com/bash/tip_colors_and_formatting)
