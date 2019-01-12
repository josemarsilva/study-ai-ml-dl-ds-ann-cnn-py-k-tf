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

### 2.2.1. Variáveis

* JupyterNotebook deste exercício disponível [Variables.ipynb](src/ipynb/02-PythonVariables/Variables.ipynb)
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


### 2.2.2. Operadores

* JupyterNotebook deste exercício disponível [Operators.ipynb](src/ipynb/03-PythonOperators/Operators.ipynb)
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

* JupyterNotebook deste exercício disponível [Operators.ipynb](src/ipynb/04-StringVariables/StringVariables.ipynb)
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


### 2.2.4. Entrada de dados

* JupyterNotebook deste exercício disponível [Operators.ipynb](src/ipynb/05-EntradaDeDados/EntradaDeDados.ipynb)
* Permite que você entre valores para um trecho de programa
* A função `input()` sempre retorna valores String!!! Lembrando que o Python dificilmente faz conversão implícitas, então se estiver lendo um número e queira fazer operações aritméticas, você precisará convertê-lo

```ipynb
idade = input('Entre a sua idade: ')
Entre a sua idade: 20
20
type(idade)
str

idade = int(input('Digite o valor numérico de sua idade: '))
Digite o valor numérico de sua idade: 20
type(idade)
int
idade + 10
30

var_pi = float(input('Digite o número pi: '))
Digite o número pi: 3.1415
var_pi
3.1415
```

* A entrada de dados é um ponto frágil dos sistemas, você precisará tratar o tipo de entrada

```ipynb
idade = int(input('Digite a sua idade: '))
Digite a sua idade: texto
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-10-3d9bb7317af4> in <module>()
----> 1 idade = int(input('Digite a sua idade: '))
ValueError: invalid literal for int() with base 10: 'string'
```


### 2.2.5. Condições

* JupyterNotebook deste exercício disponível [Operators.ipynb](src/ipynb/06-Condicoes/Condicoes.ipynb)
* Python utiliza deslocamente de texto para identar o programa. Não possui marcações do tipo ( begin, end )
* As [Condições](https://www.tutorialspoint.com/python/python_if_else.htm) : `if ( condição ):`, `else:` e `elif ( condição ):`

```ipynb
idade = 20
if (idade >= 18):
   print ('Maior de idade')
else:
  print ('Menor de idade')
```

```txt
Maior de idade
```

* Estruturas aninhadas de vários `if` e `else`

```ipynb
idade = 20
if (idade >= 18):
    if (idade >= 60 ):
        print( 'Idoso')
    else:
        print ('Adulto')
else:
  print ('Menor de idade')
```

```txt
Adulto
```

* O código pode ficar mais legível utilizando `elif` e com deslocamentos de textos de marcação desnecessários

```ipynb
opcao = 3
if (opcao == 1):
    preco = 15
elif (opcao == 2):
    preco = 20
elif (opcao == 3):
    preco = 30
else:
    preco = 50
print( 'Preco é %i' % preco)
```

```txt
Preco é 30
```


### 2.2.6. Repetições

* JupyterNotebook deste exercício disponível [Operators.ipynb](src/ipynb/07-Repeticoes/Repeticoes.ipynb)

```ipynb
count = 1
while count <= 10:
    print(count, ' ')
    count += 1 # count = count + 1
```

```txt
1 2 3 4 5 6 7 8 9 10
```

```ipynb
count = 1
while True:
    if (count % 2 == 0):
        print (count)
    count += 1
    if (count == 10):  # não vai imprimir o 10
        break
```

```txt
2 4 6 8
```

```ipynb
tabuada = 1
while tabuada <= 10:
    numero = 1
    while numero <= 10:
        print ('%i x %i = %i' % (tabuada, numero, tabuada * numero))
        numero += 1
    tabuada +=1
```


### 2.2.7. Listas

* JupyterNotebook deste exercício disponível [Operators.ipynb](src/ipynb/08-Listas/Listas.ipynb)
* As [Listas](https://docs.python.org/3/tutorial/introduction.html#lists) é um tipo de variável que permite o armazenamento de vários valores acessados por um índice
* Você pode consultar os métodos aplicáveis a uma lista `help(list)`
* As listas são estruturas que podemm armazenar informções heterogêneas, isto é de tipos de dados difrentes. Ex: int, String, Double, etc

```ipynb
help(list)
```

```ipynb
lista = [2, 'josemar', 3.1415, [ 'azul', 'vermelho', 'preta' ] ]
print(len(lista))
print(lista)
print('Último elemento da lista: ', lista[-1])
print('Último elemento da sublista que é o último elemento da lista: ', lista[-1][-1])
print('Os dois últimos elementos da sublista: ', lista[-1][-2:])
print('Primeiro elemento da lista: ', lista[0])
```

```txt
4
[2, 'josemar', 3.1415, ['azul', 'vermelho', 'preta']]
Último elemento da lista:  ['azul', 'vermelho', 'preta']
Último elemento da sublista que é o último elemento da lista:  preta
Os dois últimos elementos da sublista:  ['vermelho', 'preta']
Primeiro elemento da lista:  2
```

* As listas são **mutáveis** isto é você pode alterar o conteúdo da lista

```ipynb
lista[0] = 1
print(lista)
```

```ipynb
[1, 'josemar', 3.1415, ['azul', 'vermelho', 'preta']]
```

* Loop de repetição iterando sobre os elementos de uma lista

```ipynb
lista = [1, 2, 3, 4]
cont = 1
while cont <= len(lista):
    print(lista[cont-1], ' ')
    cont +=1
```

```txt
1 2 3 4
```

* Fatiamento

```ipynb
# fatiamento dos últimos 3 elementos
lista = [1, 2, 3, 4, 5, 6 ]
print(lista[-3:])
```

```txt
[4, 5, 6]
```

* Lista é um recurso muito poderoso, mas cuidado para algumas pegadinhas.  Em Python tudo é objeto, quando fazemos a atribuição de um objeto a outro é uma cópia da mesma referência e não o conteúdo de seus dados

```ipynb
lista1 = [1,2,3,4,5,6]
lista2 = lista1 # a atribuição de um objeto a outro é uma cópia da mesma referência
lista2[0] = 10
print('Lista1: ', lista1)
```

```txt
Lista1:  [10, 2, 3, 4, 5, 6]
```

* Para fazer cópia do conteúdo

```ipynb
lista1 = [1,2,3,4,5,6]
lista2 = lista1[:] # 
lista2[0] = 10
print('Lista1: ', lista1)
```

```txt
Lista1:  [1, 2, 3, 4, 5, 6]
```

* Para **adicionar** elementos heterogêneos ao final da lista (observe que não precisa ser do mesmo tipo) use o `append()`

```ipynb
lista1 = [1,2,3,4,5]
lista1.append('josemar')
print(lista1)
[1, 2, 3, 4, 5, 'josemar']
```

* Para **concatenar** uma lista ao final de outra pode-se utilizar o próprio operador `+`

```ipynb
lista1 = [1,2,3,4,5]
lista2 = [6,7,8,9,10]
lista_1_e_2 = lista1 + lista2
print (lista_1_e_2)
```

* Para **remover** um elementos de uma lista passando o índice da posição (iniciando em zero) 

```ipynb
lista = [1,2,3,4,5]
lista.pop(0)
print(lista)
[2, 3, 4, 5]
```

* Para **remover** um elementos de uma lista passando o elemento a ser removido

```ipynb
lista = [ 'josemar', 1, 3.1415, ['branco', 'preto'] ]
lista.remove('josemar')  # porém o elemento deve existir na lista senão dará erro
print(lista)
[1, 3.1415, ['branco', 'preto']]
```


### 2.2.8. Estrutura de Repetição FOR

* JupyterNotebook deste exercício disponível [Operators.ipynb](src/ipynb/09-EstruturaRepeticaoFor/EstruturaRepeticaoFor.ipynb)

```ipynb
lista = [1,2,3,4,5]
for e in lista:
    print (e, ' ') # itera por cada um dos elementos da lista
```

```txt
1 2 3 4 5
```

* Busca de um elemento dentro de uma lista

```ipynb
lista = [ 1, 2, 3, 4, 5]
busca = 3
for e in lista:
    if e == busca:
        print('Achou ', e)
        break # interrompe o loop
```

```txt
Achou  3
```

* Função `range()` retorna um gerador

```ipynb
# RANGE
for i in range(10):
    print(i, end=' ')
```

```txt
0 1 2 3 4 5 6 7 8 9 
```

```ipynb
# RANGE
for i in range(2,10,2): # inicio, até intervalo aberto, salto
    print(i, end=' ')
```




# Referências

* [Jupyter Notebook - Org](https://jupyter.org/)
* [Getting Started With Jupyter Notebook for Python](https://www.youtube.com/watch?v=CwFq3YDU6_Y)
* [Tutorial do Notebook Jupyter: Introdução, Configuração e Passo a Passo](https://www.youtube.com/watch?v=HW29067qVWk&t=72s)
* [Python Tutorial](https://docs.python.org/3/tutorial/)
* [Python Documentação](https://docs.python.org/3/library/index.html)
