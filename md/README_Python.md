# Python

## 1. Introdução ##

Neste capítulo separei referências para o Jupyter Notebook.

## 2. Documentação

## 2.1. Guia de Instalação

* Faça o download do Python 3.x.x de https://www.python.org/downloads/ e instale
* Instale o Jupyter Notebook pelo Pip3

```cmd
pip3 install jupyter
```

## 2.2. Guia de Programação

### 2.2.1. Variáveis em Python

* JupyterNotebook deste exercício disponível [PythonVariables.ipynb](src/ipynb/02-PythonVariables/PythonVariables.ipynb)
* Aspas duplas ou simples delimitam o string
* Nome de variáveis: iniciado por letras, seguido de letras ou números ou underscore
  * O que não pode: começar com números ou ter espaços
  * Em Python tudo são objetos, não é uma linguagem fortemente tipada, isto é possui tipagem dinâmica
  * Em Python variáveis não são caixas, são rótulos identificam objetos (o objeto já existe antes de ele ser atribuído, variável não contém objetos, isto é possui referências para o objeto)
  * Os nomes são case sensitive, isto é True (correto) é diferente de (true)
  * Objetos mutáveis: listas, dicionários
  * Objetos imutáveis:
  
```ipynb
idade = 10
print (idade)
var_pi = 3.14
print (var_pi)
type(var_pi)
```

```txt
10
3.14
float
```

```ipynb
aprovado = True
print(aprovado)
resultado = False
print(resultado)
```

```txt
True
False
```


### 2.2.2. Operadores em Python

* JupyterNotebook deste exercício disponível [PythonOperators.ipynb](src/ipynb/03-PythonOperators/PythonOperators.ipynb)
* Operadores relacionais

```ipynb
# == igualdade
# >  maior que
# <  menor que
# != diferente
# >= maior ou igual
# <= menor ou igual

# O resultado será sempre True ou Fase
n1 = 10
n2 = 20
print (n1 >  n2 )
print (n1 <  n2 )
print (n1 == n2 )
print (n1 >= n2 )
```

```txt
False
True
False
False
```

* Operadores aritméticos

```ipynb
# +, -, * , /
# // duas barras é divisão somente parte inteira
v1 = 10
v2 = 20
print ( v1 + v2 )
print ( v1 * v2 )
print ( v2 / v2 )  # resultado ponto flutuante
print ( v2 // v1 ) # força divisão inteiro
print ( v2 % v1 )  # resto da divisão
base = 2
expoente = 10
resultado = base ** expoente  # exponenciação
print (resultado)
```

```txt
30
200
1.0
2
0
1024
```


* Operadores lógicos

```ipynb
# not -> não negação (operador unário, só precisa de um termo)
# and -> conjunção
# or  -> disjunção
aprovado = True
reprovado = not aprovado
print(aprovado)
print(reprovado )
```

```txt
True
False
```


### 2.2.3. String

* JupyterNotebook deste exercício disponível [PythonOperators.ipynb](src/ipynb/04-StringVariables/StringVariables.ipynb)
* Lembre-se que em Python tudo é um objeto. Um string é um objeto que vem com métodos que podem ser executados
* Lembre-se que o String é imutável, você não pode mudar o seu conteúdo

```ipynb
nome = "josemar"  # aplica o rótulo "nome" ao objeto cadeia de string "josemar"
print(nome)
print(type(nome)) # mostra o tipo do objeto no caso string
print(nome[0])    # o String é um vetor que pode ser acessado de forma indexada iniciado por 0
print(nome[-1])   # o índice negativo mostra de traz para frente
print(nome[0:4])  # fatiamento permite com 2 argumentos separado por : que significa "de" "até"
print(len(nome))  # o método len() retorna o tamanho da String
print(nome[4:])   # fatiamento permite omitir o segundo argumento (substituído até o fim)
print(nome[-3:])  # fatiamento também pode ser negativo
print(nome[10])   # se indexar o String fora do tamanho ocorre um erro
```

```txt
josemar
<class 'str'>
j
r
jose
7
mar
mar
---------------------------------------------------------------------------
IndexError                                Traceback (most recent call last)
<ipython-input-34-f43485db6c99> in <module>()
      8 print(nome[4:])   # fatiamento permite omitir o segundo argumento (substituído até o fim)
      9 print(nome[-3:])  # fatiamento também pode ser negativo
---> 10 print(nome[10])   # se indexar o String fora do tamanho ocorre um erro

IndexError: string index out of range
```

```ipynb
nome = "Josemar"
sobrenome = "Silva"
nome_completo = nome + ' ' + sobrenome
print(nome_completo)
# Caso especial de concatenação é multiplicar a quantidade de vezes pelo que se quer imprimir
print(3*nome_completo)
```

```txt
Josemar Silva
Josemar SilvaJosemar SilvaJosemar Silva
```

* Marcador de posição de strings

```ipynb
# %d -> inteiros
# %s -> string
# %f -> decimais flutuantes
nome = "João"
idade = 20
nome_namorada = "Maria"
altura_media = 1.60
print( "%s tem %d anos e namora %s. Altura média deles é %f" % (nome, idade, nome_namorada,altura_media))

```

```txt
João tem 20 anos e namora Maria. Altura média deles é 1.600000
```



# Referências

* [Jupyter Notebook - Org](https://jupyter.org/)
* [Getting Started With Jupyter Notebook for Python](https://www.youtube.com/watch?v=CwFq3YDU6_Y)
* [Tutorial do Notebook Jupyter: Introdução, Configuração e Passo a Passo](https://www.youtube.com/watch?v=HW29067qVWk&t=72s)
* [Python Tutorial](https://docs.python.org/3/tutorial/)
* [Python Documentação](https://docs.python.org/3/library/index.html)
