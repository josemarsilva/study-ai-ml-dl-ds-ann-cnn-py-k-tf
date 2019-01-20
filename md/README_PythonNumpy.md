# README Python Numpy

## 1. Introdução ##
NumPy é um pacote de computação científica com Python. É muito poderoso, você pode construir um objeto array n-dimensional. Ele é baseado em C, portanto é mais performático. Para instalar você deve fazer:

```cmd
pip install numpy
```

## 2. Guia de Uso

* Jupyter-Notebook deste exercício disponível [PythonNumPy.ipynb](../src/ipynb/04-PythonNumPy/PythonNumPy.ipynb)

## 2.1. Import da biblioteca
Para utilizar você deve importar a biblioteca numpy

```cmd
import numpy
```

## 2.2. Matrizes n-dimensional
* Criação, inicialização
* Acessando elementos (n, m)
* Acessando a linha toda ou a coluna toda
* Transposição da matriz
* Operações com matrizes: soma, subtração, multiplicação
* Soma de elementos de um array n-dimensional
* Maior e Menor elemento de um array n-dimensional

```ipynb
m = numpy.array([(1,2),(3,4)])
print('Elemento da 2a linha e 2a coluna: ', m[1][1]) # lembrando que a indexação é a partir do 0
print('... também é possível: ', m[-1][-1])          # também posso acessar pela última linha
print('Segunda linha da matriz: ', m[1:])            # acessando toda a última linha
print('Primeira coluna da matriz: ', m[:,0])         # acessando toda a primeira coluna
print('Matriz Transposta: ')
print(m.transpose())        # matriz transposta
m1 = numpy.array([(1,2,3),(4,5,6)])
m2 = numpy.array([(7,8,9),(10,11,12)])
print('\nOperações com matrizes: ')
print('m1:\n', m1)
print('m2:\n', m2)
print('m1+m2:\n', m1+m2)
print('m2-m1:\n', m2-m1) # elemento por elemento a diferença
print('m1*m2:\n', m1*m2) # lembrando que número de colunas de m1 tem que ser igual ao número de colunas de m2
a1 = numpy.array([1,2,3,4,5,6])
print('a1:\n', a1)
print('array - a1.sum(): ', a1.sum())
print('matriz - m1.sum():', m1.sum())
print('array - a1.argmax()', a1.argmax(), ' - atenção que o retorno é o índice do array')
print('array - a1.argmin()', a1.argmin(), ' - atenção que o retorno é o índice do array')
```

```txt
Elemento da 2a linha e 2a coluna:  4
... também é possível:  4
Segunda linha da matriz:  [[3 4]]
Primeira coluna da matriz:  [1 3]
Matriz Transposta: 
[[1 3]
 [2 4]]

Operações com matrizes: 
m1:
 [[1 2 3]
 [4 5 6]]
m2:
 [[ 7  8  9]
 [10 11 12]]
m1+m2:
 [[ 8 10 12]
 [14 16 18]]
m2-m1:
 [[6 6 6]
 [6 6 6]]
m1*m2:
 [[ 7 16 27]
 [40 55 72]]
a1:
 [1 2 3 4 5 6]
array - a1.sum():  21
matriz - m1.sum(): 21
array - a1.argmax() 5  - atenção que o retorno é o índice do array
array - a1.argmin() 0  - atenção que o retorno é o índice do array
```


## 2.3. NumPy Array vs Listas do Python
* NumPy Arrays são mais compactos - consomem menos memória
* NumPy Arrays são mais eficientes - acessos leituras e escritas são muito mais rápidos
* Para computação científica vale muito a pena uso do NumPy

```ipynb
import numpy as np
m1 = np.array([(2,4),(6,8)])
# abaixo digite "a." em seguida <TAB> e mostra a lista de operações que você pode fazer com NumPy
print('Média (mean):\n', m1.mean())
print('Diagonal:\n', m1.diagonal())
```

```txt
Média (mean):
 5.0
Diagonal:
 [2 8]
```

```ipynb
lista = [1, 2, 3, 'josemar']
# abaixo digite "lista." em seguida <TAB>
```

## 2.4. Eficiência do NumPy
* O NumPy é muito mais eficiente nas interaçoes: Soma de elementos

```ipynb
soma = 0
for i in range(1, 100000001): # 1 seguido de 7 x zeros + 1
    soma += i
```

```ipynb
import numpy as np
np.arange(1,100000001).sum()
```


## 2.4. Fatiamento (Slice) em NumPy

```ipynb
lista = [10, 20, 30, 40]
print('Lista - Fatiamento - do índice 1 ao índice 1 (aberto)', lista[1:2]) # >= i && < j
print('Lista - Fatiamento - o terceiro termo é o salto', lista[::2])       # a partir do primeiro elemento, até o final, saltando 2 posições
```

```txt
Lista - Fatiamento - do índice 1 ao índice 1 (aberto) [20]
Lista - Fatiamento - o terceiro termo é o salto [10, 30]
```

```ipynb
import numpy as np
a = np.array(lista)
print('NumPy - Fatiamento - do indice 1', a[1:2])
print('NumPy - Fatiamento - o terceiro termo é o salto', a[::2])
```

```txt
NumPy - Fatiamento - do indice 1 [20]
NumPy - Fatiamento - o terceiro termo é o salto [10 30]
```


## 2.5. NumPy vs Lista - Cópia do conteúdo vs cópia do Label (endereço de memória)
* Usando Listas a atribuição de uma nova lista consiste na criação de um ponteiro para o mesmo elemento
* Usando NumPy Array a atribuição de um novo array implica também na criação de um ponteiro para o mesmo elemento
* Usando NumPy Array, para se tirar uma cópia do dados, de forma que se eles forem alterados não impactar o objeto original, isto deve ser feito com copy

```ipynb
l1 = [1,2,3,4,5]
l2 = l1 # Em listas a atribuição é apenas um novo rótulo para o mesmo objeto
l1[0] = 999 # veja que a atribuição foi feita em l1 mas também afeta l2
print('l1:\n', l1) 
print('l2:\n', l2)

import numpy as np
a1 = np.array([1,2,3,4,5])
a2 = a1[:]
a2[0] = 999
print('a1:\n', a1)
print('a2:\n', a2)
a3 = np.array([1,2,3,4,5])
a4 = a3.copy()  # aqui o conteúdo de memoria foi copiado e criado um novo endereço
a3[0] = 888
print('a3:\n', a3)
print('a4:\n', a4)
```

```txt
l1:
 [999, 2, 3, 4, 5]
l2:
 [999, 2, 3, 4, 5]
a1:
 [999   2   3   4   5]
a2:
 [999   2   3   4   5]
a3:
 [888   2   3   4   5]
a4:
 [1 2 3 4 5]
```



# Referências

* [Vídeo **muito bom** Python: NumPy Numerical Python Arrays Tutorial](https://www.youtube.com/watch?v=8Mpc9ukltVA&list=PLORrDfZD1hkFD3HcJVoBsQoXf2BmnUt65)
* [Vídeo Python NumPy Tutorial - NumPy Array - Python Tutorial For Beginners - Python Training - Edureka](https://www.youtube.com/watch?v=8JfDAm9y_7s)
* http://www.numpy.org/
* https://www.datacamp.com/community/tutorials/python-numpy-tutorial
* https://docs.scipy.org/doc/numpy/user/quickstart.html