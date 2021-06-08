# README_Python.md

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

* Jupyter-Notebook deste exercício disponível [Variables.ipynb](../src/ipynb/01-PythonLanguage/02-Variables.ipynb)
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

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/03-Operators.ipynb)
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

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/04-StringVariables.ipynb)
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

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/05-EntradaDeDados.ipynb)
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

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/06-Condicoes.ipynb)
* As [Condições](https://www.tutorialspoint.com/python/python_if_else.htm) : `if ( condição ):`, `else:` e `elif ( condição ):`
* Python utiliza deslocamento de texto para identar o programa. Não possui marcações do tipo ( begin, end )

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

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/07-Repeticoes.ipynb)

```ipynb
count = 1
while count <= 10:
    print(count, end=' ')
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

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/08-Listas.ipynb)
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
    print(lista[cont-1], end=' ')
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

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/09-EstruturaRepeticaoFor.ipynb)
* [FOR](https://docs.python.org/3/tutorial/controlflow.html#for-statements) mecanismo de repeticao

```ipynb
lista = [1,2,3,4,5]
for e in lista:
    print (e, end=' ') # itera por cada um dos elementos da lista
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


### 2.2.9. Tuplas

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/10-Tuplas.ipynb)
* [Tupla](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences) é um objeto **imutável**. Seu estado é congelado na inicialização e não se pode mais modificá-lo.
* A representação de tupla é parênteses: "(" e ")". Lembrando que a representação de listas é colchetes: "[" e "]"
* Tupla também é **heterogêneas** assim como a lista
* Para saber os métodos de uma tupla pode usar o help `help(tuple)`


```ipynb
tupla = ( 1, 'josemar', 3.1415)
print(tupla[0]) # Indexavel
print(tupla[-2:])
```

```txt
1
('josemar', 3.1415)
```

```ipynb
tupla = ( 1, 2, 2, 3, 3, 3, 4, 4, 4, 4)
print('count(3): ' , tupla.count(3)) # conta quantas vezes o 3 aparece
print('index(4): ' , tupla.index(4)) # retorna o índice do primeiro 4 se não existir dará erro 
print('len(): ',     len(tupla))     # tamanho
```

```txt
count(3):  3
index(4):  6
len():  10
```


### 2.2.10. Conjuntos

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/11-Conjuntos.ipynb)
* [SET](https://docs.python.org/3/tutorial/datastructures.html#sets) são estruturas utilizadas para representar coleções **desordenadas** de elementos **únicos**
* Conjuntos **não suportam** indexação, fatiamento, não podemos ter confiança na ordem que será apresentado
* Você pode fazer operações com conjuntos: `union()`, `intersection()`, `difference()`

```ipynb
s = set()
s.add(10)
s.add(20)
s.add(20) # repetido será ignorado
s.add(30)
s.add(30) # repetido será ignorado
s.add(30) # repetido será ignorado
print(s)
```

```txt
{10, 20, 30}
```

```ipynb
s1 = {2,1,3,4}
s2 = {4,7,5,6,8}
uniao = s1.union(s2)
print('Uniao: ', uniao)
itersecao = s1.intersection(s2)
print('Intersection: ', itersecao)
diferenca = s1.difference(s2)
print('Difference: ', diferenca)
```

```txt
Uniao:  {1, 2, 3, 4, 5, 6, 7, 8}
Intersection:  {4}
Difference:  {1, 2, 3}
```
 
* Suponha que você tenha uma lista com elementos repetidos e queira imprimir todos os elementos sem repetição

```ipynb
lista = [1,2,2,3,3,3,4,4,4,4,5,5,5,5,5,0,-1,-2,-2,-3,-3,-3]
conjunto = set(lista)
print('Lista: ', lista)
print('Conjunto: ', conjunto)
lista2 = list(conjunto)
print('Lista2: ', lista2)
```

```
Lista:  [1, 2, 2, 3, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 5, 0, -1, -2, -2, -3, -3, -3]
Conjunto:  {0, 1, 2, 3, 4, 5, -2, -3, -1}
Lista2:  [0, 1, 2, 3, 4, 5, -2, -3, -1]
```


### 2.2.11. Dicionários

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/12-Dicionarios.ipynb)
* [Dicionários](https://docs.python.org/3/tutorial/datastructures.html#dictionaries) são estruturas de dados semelhantes às listas, mas com propriedades de acesso diferentes. Ele é composto por um conjunto de (chave, valor). Dicionários são **mutáveis** e **heterogêneos**.
* A principal diferença entre listas e dicionários, é que o método de acesso do dicionário é a chave e o da lista o índice
* Você pode iterar pelo dicionário com o `for`

```ipynb
d = {'josemar': 49, 'maria': 45, 'guilherme': 25, 'gabrielle': 17}
print('dicionário todo: ', d)
print('indexando pela chave', d['guilherme']) # se a chave não existir vai dar erro
d['melanie'] = 'pet da família' # dicionários são mutáveis, podem receber alterações e são heterogêneos
print('todo dicionário novamente: ', d)

print('chaves dos elementos: ', end=' ')
for e in d:
    print(e, end=' ')

print('')
print('valores dos elementos', end=' ')
for e in d:
    print(d[e], end=' ')


print('Imprimir os elementos do dicionário de uma vez só: ', d.items() )
print('Imprimir as chaves do dicionário de uma vez só: ', d.keys() )
print('Imprimir os valores do dicionário de uma vez só: ', d.values() )
```

```txt
dicionário todo:  {'josemar': 49, 'maria': 45, 'guilherme': 25, 'gabrielle': 17}
indexando pela chave 25
todo dicionário novamente:  {'josemar': 49, 'maria': 45, 'guilherme': 25, 'gabrielle': 17, 'melanie': 'pet da família'}
chaves dos elementos:  josemar maria guilherme gabrielle melanie 
valores dos elementos 49 45 25 17 pet da família Imprimir os elementos do dicionário de uma vez só:  dict_items([('josemar', 49), ('maria', 45), ('guilherme', 25), ('gabrielle', 17), ('melanie', 'pet da família')])
Imprimir as chaves do dicionário de uma vez só:  dict_keys(['josemar', 'maria', 'guilherme', 'gabrielle', 'melanie'])
Imprimir os valores do dicionário de uma vez só:  dict_values([49, 45, 25, 17, 'pet da família'])
True
```

```ipynb
print( 'maria está no dicionário? ', 'maria' in d )
print( 'inexiste está no dicionário?' , 'inexiste' in d )
```

```txt
maria está no dicionário?  True
inexiste está no dicionário? False
```


### 2.2.12. Criando Funções

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/13-CriandoFuncoes.ipynb)
* Uma função pode ter o número de argumentos de parâmetros dinâmico: `func(*args):` ou opcionais com valores defaults `imprimir(nome='desconhecido')`
* Uma função também é um objeto, e pode chamar a ela mesma (recursividade)
* Python pode chamar funcoes La

```ipynb
def somar(n1, n2):
    return n1 + n2

print('resultado da funcao :' , somar( 1, 2) )

def retorna_qualquer_coisa():
    return "qualquer_coisa"

print ( retorna_qualquer_coisa() )

def eh_par(n):
    return n % 2 == 0;

print(eh_par(1));
print(eh_par(2));
```

```txt
resultado da funcao : 3
qualquer_coisa
False
True
```



### 2.2.13. Mòdulos

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/14-Modulos.ipynb)
* Um módulo nada mais é do que um arquivo .py que deverá ser importado em seu programa
* No Jupyter-Notebook a [sintaxe](https://stackoverflow.com/questions/21034373/how-to-load-edit-run-save-text-files-py-into-an-ipython-notebook-cell) é `%load` isto provoca a 


def area_quadrado(lado):
    return lado * lado

def area_retangulo(lado1, lado2):
    return lado1 * lado2

def perimetro_quadrado(lado):
    return 4 * lado

# agora coloque estas 3 funções em um arquivo chamado my_module.py
```ipynb

* Se você estiver usando o Jupyter-Notebook Então vamos forçar o Jupyter-Notebook a reiniciar `Menu :: Kernel >> Restart & Clear Output` desta forma temos certeza que as definições destas funções se foram
* Para carregar o arquivo de módulo faça: `%load my_module.py`
* O trecho abaixo só vai funcionar em linha de comando ou se você colocar o arquivo `my_module.py` na pasta do Jupyter-Notebook
* Import universal: `from math import *` importa todas as definições. É perigoso porque dois módulos podem importar uma mesma função com o mesmo nome e a que fica valendo é a última importada, logo é uma **boa prática** sempre ser específico nas funções de sua importação.

```ipynb
from my_module import area_quadrado
from my_module import area_retangulo
from my_module import perimetro_quadrado

print(area_quadrado(2))
print(area_retangulo(3,4))
print(perimetro_quadrado(3))
```

```txt
4
12
12
```

* importando bibliotecas de sistemas

```ipynb
import math
print('factorial: ', math.factorial(5))
print('sqrt: ', math.sqrt(25))
```

```ipynb
factorial:  120
sqrt:  5.0
```


### 2.2.14. Arquivos

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/15-CriandoArquivos.ipynb)
* Um módulo nada mais é do que um arquivo .py que deverá ser importado em seu programa

```ipynb
# Funcao: open( especificação do arquivo, modos)

arq = open('teste-arquivo.txt', 'w' ) # abre o arquivo para escrita
arq.write('escrevi qualquer coisa')   # escrevemos alguma coisa no arquivo
arq.write('\ne oura coisa')   # escrevemos alguma coisa no arquivo
arq.close()                           # fechei o arquivo

texto = '''
Aprendendo Python
Machine Learning
Esta muito facil
'''
arq = open('teste-arquivo.txt', 'a' ) # abre o arquivo para escrita ao seu final
arq.write(texto)
arq.close()

with open('teste-arquivo-2.txt', 'w' ) as f: # abre o arquivo para escrita
    f.write(texto)
```

* veja o conteúdo dos arquivos `teste-arquivo.txt` e `teste-arquivo-2.txt` na mesma pasta de seu Jupyter-Notebook

```ipynb
with open('dataset.txt', 'r') as f: 
    print(f.readlines())

with open('dataset.txt', 'r') as f: 
    for line in f.readlines():
        print(line)
		
with open('dataset.txt', 'r') as f: 
    lista = f.read().splitlines()
    print(lista)

print('Somente primeiro elemento da lista: ', lista[0])
```


### 2.2.15. Orientacao Objeto

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/16-OrientacaoObjeto.ipynb)
* Python é uma linguagem com múltiplos paradigmas, inclusive **orientação a objeto**
* Em Python tudo é um objeto
* Para definir uma [classe](https://docs.python.org/3.7/tutorial/classes.html) em Python, utiliza-se a palavra chave `class`
* Em Python os métodos também são atributos

```ipynb
class Conta:
    
    def __init__(self, nome_cliente, numero_conta):
        self.nome_cliente = nome_cliente
        self.numero_conta = numero_conta

class  ContaEspecial(Conta): # herda da superclasse Conta
    
    def __init__(self, nome_cliente, numero_conta, limite=0):
        Conta.__init__(self, nome_cliente, numero_conta) # acionando o construtor da superclasse
        self.limite = limite
        
conta = ContaEspecial( 'josemar', '1234-5', 100)
print('Titular:', conta.nome_cliente)
print('No.Conta:', conta.numero_conta)
print('Limite:', conta.limite)

print('type do objeto conta:', type(conta))
```

```txt
Titular: josemar
No.Conta: 1234-5
Limite: 100
type do objeto conta: <class '__main__.ContaEspecial'>
```


### 2.2.16. Programação Funcional

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/01-PythonLanguage/17-ProgramacaoFuncional.ipynb)
* Python é uma linguagem com múltiplos paradigmas, inclusive **funcional**. Para uma programação funcional, os resultados retornados por uma função deve depender unicamente dos parâmetros de entrada. Você é obrigado a quebrar o seu programa em pequenos pedaços, é mais fácil de debugar, etc.
* Expressões `lambda` são pequenas funções anônimas.
* Função `filter` aplica uma função a uma sequencia ou lista
* Função `map` também recebe como parâmetro uma função mas o resultado da função é calculado sobre cada elemento da sequencia

```ipynb
dobro = lambda x: x * 2                          # lambda
dobro(5)
soma = lambda x, y: x + y                        # lambda n parâmetros
soma(1, 2)
lista = [1,2,3,4,5,6,7,8,9,10]
list( filter(lambda par: par % 2 == 0, lista) )  # filter
list(map(lambda duplica: duplica * 2, lista))    # map
```

```txt
10
3
[2, 4, 6, 8, 10]
[2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```


## 2.3. Exercícios em Python

### 2.3.1. Orientação Objeto - Jogo matriz de recompensa
Vamos fazer um joguinho que permita que um robô ande por uma matriz 10x10 e encontre recompensas. Iremos utilizar Orientação a Objetos (OO) em Python.

* Jupyter-Notebook deste exercício disponível [Operators.ipynb](../src/ipynb/02-PythonOrientacaoObjeto/01-JogoMatrizRecompensa.ipynb)
* Relembrando: em Python tudo é objeto
* O primeiro parâmetro é `self` que informa a instância do objeto da classe. Pode ser omitido
* O método `__init__` é uma convenção para o construtor
* Uma classe pode herdar as características de outra, para tal em sua definição deve explicitar a super classe `class ClasseFilha(ClasseSuper):`
* O método `__str__` é uma convenção de impressão dos dados de um objeto

* **Classe Ponto**: define um ponto no tabuleiro da matriz 10 x 10

```ipynb
class Ponto:
    
    def __init__(self, x, y):
        self.x = x
        self.y = y
        
    def __str__(self):
        return '<%s, %s>' % (self.x, self.y)   
```

* **Classe Recompensa**: Define uma recompensa que o Robo pode pegar se passar pela posição
```ipynb
class Recompensa(Ponto):
    
    def __init__(self, x, y, nome):
        super(Recompensa, self).__init__(x, y)
        self.nome = nome
        
    def __str__(self):
        return '<%s, %s, %s>' % (self.x, self.y, self.nome)
    
    def __repr__(self):
        return self.__str__()
```

* **Classe Robo**: Define o robo que tem uma posição(x,y) e faz movimentos (up, down, left, right)
```ipynb
class Robo:
    
    def __init__(self, x, y):
        self.x = x
        self.y = y
        
    def __str__(self):
        return '<%s,%s>' % (self.x, self.y)

    def move_up(self):
        if self.y < 10:
            self.y = self.y + 1
        else:
            print('movimento(y+1) invalido!')

    def move_down(self):
        if self.y > 0:
            self.y = self.y - 1
        else:
            print('movimento(y-1) invalido!')

    def move_right(self):
        if self.x < 10:
            self.x = self.x + 1
        else:
            print('movimento(x+1) invalido!')

    def move_left(self):
        if self.x > 0:
            self.x = self.x - 1
        else:
            print('movimento(x-1) invalido!')

r1 = Robo(5,5)
print('Robo r1 (%i,%i)' % (r1.x, r1.y))
print(r1)
```

* **Função check_recompensa**: Verifica se o robo, na posição onde está, pegou alguma recompensa. Caso afirmativo mostra a lista.

```ipynb
def check_recompensa(robo, recompensas):
    retorno = False
    for recompensa in recompensas:
        if recompensa.x == robo.x and recompensa.y == robo.y:
            print('robo achou a recompensa %s' % recompensa.nome) # mostra todas as recompensas que o robo pode ter pego
            retorno = True
    return retorno
```

* **Bloco principal - Parte 1**: Cria a lista de recompensas

```ipynb
import random
recompensa1 = Recompensa(random.randint(0,10), random.randint(0,10), 'moeda')
recompensa2 = Recompensa(random.randint(0,10), random.randint(0,10), 'gasolina')
recompensa3 = Recompensa(random.randint(0,10), random.randint(0,10), 'arma')
recompensa4 = Recompensa(random.randint(0,10), random.randint(0,10), 'moeda')
recompensa5 = Recompensa(random.randint(0,10), random.randint(0,10), 'gasolina')
recompensa6 = Recompensa(random.randint(0,10), random.randint(0,10), 'arma')
recompensa7 = Recompensa(random.randint(0,10), random.randint(0,10), 'moeda')
recompensa8 = Recompensa(random.randint(0,10), random.randint(0,10), 'gasolina')
recompensa9 = Recompensa(random.randint(0,10), random.randint(0,10), 'arma')
recompensas = [recompensa1, recompensa2, recompensa3, recompensa4, recompensa5, recompensa6, recompensa7, recompensa8, recompensa9]
```
 
* **Bloco principal - Parte 2**: Interage com o usuário pedindo os movimentos do robo, executa os movimentos e verifica se encontrou alguma recompensa em cada movimento realizado.

```ipynb
robo = Robo(random.randint(0,10), random.randint(0,10))
for i in range(0,10):
    movimento = input('Digite "up", "down", "left" ou "right"')
    if movimento == 'up':
        robo.move_up()
    elif movimento == 'down':
        robo.move_down()
    elif movimento == 'left':
        robo.move_left()
    elif movimento == 'right':
        robo.move_right()
    else:
        print('Movimento inválido!')
        continue  # não interrompe o loop e volta para o início do bloco
    print(robo)
    check_recompensa(robo,recompensas)

# No final mostra onde estão as 9 recompensas
recompensas
```



### 2.3.2. Métodos mágicos
Os métodos mágicos são métodos que por convensão você sabe que todo objeto tem e pode usar. Exemplo:
* `__init__`: é o construtor de todo objeto
* `__str__`: é o método que invocado para imprimir o objeto. O `print()` de um objeto. Quando você quer que o objeto se mostra.
* `__repr__`: é o método que invocado para mostrar a representação string o objeto



# Referências

* [Jupyter Notebook - Org](https://jupyter.org/)
* [Getting Started With Jupyter Notebook for Python](https://www.youtube.com/watch?v=CwFq3YDU6_Y)
* [Tutorial do Notebook Jupyter: Introdução, Configuração e Passo a Passo](https://www.youtube.com/watch?v=HW29067qVWk&t=72s)
* [Python Tutorial](https://docs.python.org/3/tutorial/)
* [Python Documentação](https://docs.python.org/3/library/index.html)

