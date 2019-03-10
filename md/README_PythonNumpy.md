# README Python Numpy

## 1. Introdução ##
NumPy é um pacote de computação científica com Python. É muito poderoso, você pode construir um objeto array n-dimensional. Ele é baseado em C, portanto é mais performático. Para instalar você deve fazer:

```cmd
pip install numpy
```

* ou 

```cmd
pip3 install numpy
```

---
## 2. Guia de Uso

* Jupyter-Notebook deste exercício disponível [PythonNumPy.ipynb](../src/ipynb/04-PythonNumPy/PythonNumPy.ipynb)

## 2.1. Import da biblioteca
Para utilizar você deve importar a biblioteca numpy

```cmd
import numpy
```

---
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


---
## 2.3. NumPy Array vs Listas do Python
* NumPy Arrays são mais compactos - consomem menos memória
* NumPy Arrays são mais eficientes - acessos leituras e escritas são muito mais rápidos
* Para computação científica vale muito a pena uso do NumPy
* As vantangens de **NumPy** sobre as **Listas de Python**:
  * **Economiza tempo de codificação**: Não há necessidade de loops em muitas operações de matrizes e vetores
  * **Execução mais rápida**: 
    * Um único tipo de dado para cada campo evita a necessidade de checkagem de tipo
    * Uso contíguo da memória
  * **Requerm menos memoria**:
    * Python List é um vetor de ponteiros para objetos Python: são 4 bytes por ponteiro + 16 bytes para um objeto numérico
    * **NumPy**: Não tem ponteiros, **todos** os **tipos** e os **tamanhos** dos itens **são os mesmos**

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

---
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


---
## 2.5. Fatiamento (Slice) em NumPy

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


---
## 2.6. NumPy vs Lista - Cópia do conteúdo vs cópia do Label (endereço de memória)
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


---
## 2.7. NumPy `linspace` Espacamento linear entre dois elementos
* A funçao `linespace()` gera automanticamente um espaçamento linear entre dois números

```ipynb
import numpy as np
a = np.array([2,3,4])
print('a: ', a)
b = np.arange(1,12,2) # de 1 a 12, com  saltando de 2 em 2
print('b: ' , b)
c = np.linspace(1,12,6) # de 1 a 12, com 6 elementos distribuidos linearmente
print('c: ', c)
d = np.linspace(1,2,3) # de 1 a 2, com 3 elementos
print('d: ', d)
```

```txt
a:  [2 3 4]
b:  [ 1  3  5  7  9 11]
c:  [ 1.   3.2  5.4  7.6  9.8 12. ]
d:  [1.  1.5 2. ]
```

---
## 2.8. NumPy `reshape()`, `shape` e `ndim()` - remodelando as dimensões de array
* Como os dados são armazenados de forma contíguas, as transformações do tipo um vetor n dimensões ser convertido em uma matriz de n/2 x m

```ipynb
a = np.linspace(1,12,6) # de 1 a 12, com 6 elementos distribuidos linearmente
print('a: ', a)
b = a.reshape(3,2) # remodela o vetor de 6 posiçoes para uma matriz de 3x2
print('b: ', b)
c = b.reshape(1,6) # remodela a matriz devolta para o vetor (matriz de 1 x n)
print('c: ', c)
print('a.shape: ', a.shape)
print('b.shape: ', b.shape)
print('c.shape: ', c.shape)
print('a.ndim: ', a.ndim)
print('b.ndim: ', b.ndim)
print('c.ndim: ', c.ndim)
```

```txt
a:  [ 1.   3.2  5.4  7.6  9.8 12. ]
b:  [[ 1.   3.2]
 [ 5.4  7.6]
 [ 9.8 12. ]]
c:  [[ 1.   3.2  5.4  7.6  9.8 12. ]]
a.shape:  (6,)
b.shape:  (3, 2)
c.shape:  (1, 6)
a.ndim:  1
b.ndim:  2
c.ndim:  2
```


---
## 2.9. NumPy `size()` - número total de elementos do array e `itemsize`
* a função `size()` retorna o número de elementos de um array
* a função `itemsize()` retorna o tamanho em bytes de __cada__ elemento do array. Em um array de elementos do tipo float64 o `itemsize` 8 (=64/8), enquanto o tipo complex32 tem `itemsize` 4 (=32/8). Isto é equivalente a `ndarray.dtype.itemsize`

```ipynb
a = np.linspace(1,12,6) # de 1 a 12, com 6 elementos distribuidos linearmente
b = a.reshape(3,2) # remodela o vetor de 6 posiçoes para uma matriz de 3x2
c = np.array([1,2,3,4,5,6,7,8,9,0])
print('a: ', a)
print('b: ', b)
print('c: ', c)
print('a.size(): ', a.size)
print('b.size(): ', b.size)
print('c.size(): ', c.size)
print('a.itemsize: ', a.itemsize)
print('b.itemsize: ', b.itemsize)
print('c.itemsize: ', c.itemsize)
```

```txt
a:  [ 1.   3.2  5.4  7.6  9.8 12. ]
b:  [[ 1.   3.2]
 [ 5.4  7.6]
 [ 9.8 12. ]]
c:  [1 2 3 4 5 6 7 8 9 0]
a.size():  6
b.size():  6
c.size():  10
a.itemsize:  8
b.itemsize:  8
c.itemsize:  4
```


---
## 2.10. NumPy `dtype()` - tipo de dados armazenado

```ipynb
a = np.arange(1,12,4)
b = np.linspace(1,12,6)
print('a: ', a)
print('b: ', b)
print('dtype(a): ', a.dtype)
print('dtype(b): ', b.dtype)
```

```txt
a:  [1 5 9]
b:  [ 1.   3.2  5.4  7.6  9.8 12. ]
dtype(a):  int32
dtype(b):  float64
```


---
## 2.11. NumPy vetor multi-dimensional importância do colchete [] e parenteses ()

```ipynb
a = np.array([(1,3.2,5.4),(7.6, 9.8, 12)])
print('a: ', a)
print('a.shape: ', a.shape)
print('a.size:', a.size)
print('a.dtype', a.dtype)
```

```txt
a:  [[ 1.   3.2  5.4]
 [ 7.6  9.8 12. ]]
a.shape:  (2, 3)
a.size: 6
a.dtype float64
```


---
## 2.12. NumPy operação com todos elementos do array

* Comparação de cada um dos elementos para saber se é menor do que 4
* Multiplicar cada um dos elementos por 3

```ipynb
a = np.array([(1,3.2,5.4),(7.6, 9.8, 12)])
print('a: ', a)
print('a < 4: # compara (<) cada um dos elementos com 4\n', a < 4)
print('\na * 3:\n', a * 3 )
a *= 3
print('\na:\n', a)
```

```ipynb
a:  [[ 1.   3.2  5.4]
 [ 7.6  9.8 12. ]]
a < 4: # compara (<) cada um dos elementos com 4
 [[ True  True False]
 [False False False]]

a * 3:
 [[ 3.   9.6 16.2]
 [22.8 29.4 36. ]]

a:
 [[ 3.   9.6 16.2]
 [22.8 29.4 36. ]]
```


---
## 2.13. NumPy funções `zeros()` e `ones()`

```ipynb
a = np.zeros((3,4))
print('a:\n', a)
print('a.dtype:', a.dtype)
b = np.ones((2,3))
print('b:\n', b)
print('b.dtype:', b.dtype)
c = np.ones(10)
print('c:\n', c)
```

```txt
a:
 [[0. 0. 0. 0.]
 [0. 0. 0. 0.]
 [0. 0. 0. 0.]]
a.dtype: float64
b:
 [[1. 1. 1.]
 [1. 1. 1.]]
b.dtype: float64
c:
 [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
```


---
## 2.14. NumPy  `dtype()`, `random`, `randint`, `set_printoptions`, `min()`, `max()`, `mean()` `std()`, `var()`, parâmetro `axis=n`

```ipynb
a = np.array([2,3,4], dtype=np.int16)
print('a:\n', a)
print('a.dtype:', a.dtype)
print('a.itemsize:', a.itemsize) # tamanho ocupado em bytes
b = np.random.random((2,3))
print('b:\n', b)
print('b.dtype:', b.dtype)
print('b.itemsize:', b.itemsize)
c = np.random.randint(0,10,5) # de 0 to 10 (inclusivo) com 5 elementos
print('c:\n', c)
print('c.dtype:', c.dtype)
print('c.itemsize:', c.itemsize)
print('c.sum: ', c.sum())
print('c.min: ', c.min(), '; c.max:', c.max(), ' - mean:', c.mean(), ' - std:', c.std(), ' - var:', c.var())
print('agora operações com eixo axis=n')
print('b:\n', b)
print('\nb.sum(axis=0)', b.sum(axis=0))
```

```txt
a:
 [2 3 4]
a.dtype: int16
a.itemsize: 2
b:
 [[0.9595906  0.1235567  0.90017602]
 [0.31400116 0.56075755 0.32200907]]
b.dtype: float64
b.itemsize: 8
c:
 [4 1 5 7 8]
c.dtype: int32
c.itemsize: 4
c.sum:  25
c.min:  1 ; c.max: 8  - mean: 5.0  - std: 2.449489742783178  - var: 6.0
agora operações com eixo axis=n
b:
 [[0.9595906  0.1235567  0.90017602]
 [0.31400116 0.56075755 0.32200907]]

b.sum(axis=0) [1.27359176 0.68431425 1.2221851 ]
```

---
## 2.15. Operações com matrizes
* Observe com é simples fazer operações com matrizes
* Operação de Dividir os elementos de uma matriz por outra é simplesmente m2 / m1
* Operação de Arredondamento dos elementos de uma matriz
* Operação de Multiplicação dos elementos de uma matriz
* Operação de Soma dos elementos de uma matriz
* Operação de Subtraão dos elementos de uma matriz
* Operação de Exponenciação dos elementos de uma matriz

```ipynb
import numpy as np
m1 = np.array([[1,2,3],[4,5,6]])
m2 = np.array([[7,8,9],[10,11,12]])
print('m1:\n', m1)
print('m2:\n', m2)
print('m2/m1:\n', m2/m1) # para cada elemento (i,j) de m2 aplicar a divisão pelo elemento (i,j) de m1
print('np.matrix.round(m2/m1):\n', np.matrix.round(m2/m1)) # arredondando cada um dos elementos
print('10 * m2:\n', 10 * m2)
print('m1 + 5:\n', m1 + 5)
print('m2 - 1:\n', m2 - 1)
print('m1 ** 2:\n', m1 ** 2)
```

```txt
m1:
 [[1 2 3]
 [4 5 6]]
m2:
 [[ 7  8  9]
 [10 11 12]]
m2/m1:
 [[7.  4.  3. ]
 [2.5 2.2 2. ]]
np.matrix.round(m2/m1):
 [[7. 4. 3.]
 [2. 2. 2.]]
10 * m2:
 [[ 70  80  90]
 [100 110 120]]
m1 + 5:
 [[ 6  7  8]
 [ 9 10 11]]
m2 - 1:
 [[ 6  7  8]
 [ 9 10 11]]
m1 ** 2:
 [[ 1  4  9]
 [16 25 36]]
```

---
## 2.16. Manipulação de elementos em NumPy array
* Lembre-se que as alterações de elementos em arrays retornam outro array
* o método `insert` adiciona um elemento a um array

```ipynb
import numpy as np
array = np.array([1, 2, 3])
print('array: ', array)

array:  [1 2 3]
np.insert(array,1,10) # a partir da posição 1, o elemento 10. Isto faz impressao do resultado na console ...
array([ 1, 10,  2,  3])

print('array: ', array) # ... mas array continua com o conteúdo inicial
array:  [1 2 3]
```

---
## 2.18. Manipulação de elementos em NumPy array multi-dimensional e dimensoes
* Avaliando o numero de dimensoes de um array multi-dimensional com `ndim`
* Somar os elementos de um eixo ( vertical ou horizontal ) com `sum()`
* Inserir elemento em um array-multi-dimensional com `insert()`
* Anexar elemento ao final de um array com `append()`
* Deletando elementos do array com `delete()` pode-se escolher o eixo
* Deletando elementos do array com operacoes de fatiamento `[::]`
* Repetir elementos em um array com `repeat()`

```ipynb
a = np.array([[1,2],[3,4]])
print('a:\n', a , '\n')

print('núm. dimensoes:', a.ndim)
print('Soma do eixo X (vertical): ', a.sum(axis=0)) # soma dos elementos do eixo X
print('Soma do eixo Y (horizontal):', a.sum(axis=1)) # soma dos elementos do eixo Y

np.insert(a, 1, 5, axis = 1) # axis = 1 
array([[1, 5, 2],
       [3, 5, 4]])

np.insert(a, 0, 5, axis = 0) # axis = 0 
array([[5, 5],
       [1, 2],
       [3, 4]])
```

```ipynb
b = np.array([[1,2], [3,4]])
print('b:\n', b)
np.append(b,[[5,6]]) # sem dizer qual o eixo, vai virar um array uni-dimensional
np.append(b,[[5,6]], axis=0) # dizendo o eixo volta a ser uma matriz

b:
 [[1 2]
 [3 4]]

array([[1, 2],
       [3, 4],
       [5, 6]])
```

```ipynb
b = np.array([[1,2,3],[4,5,6],[7,8,9],[10,11,12]])
print('b:\n', b)
b_ = np.delete(b,np.s_[::2],0)
print('b_(depois do delete):\n', b_)


b:
 [[ 1  2  3]
 [ 4  5  6]
 [ 7  8  9]
 [10 11 12]]
b_(depois do delete):
 [[ 4  5  6]
 [10 11 12]]
```

```ipynb
import numpy as np
a = np.array([[1,2],[3,4]])
print('a:\n', a)
np.repeat(a,2) # repetir 2 vezes cada elemento
print('\nrepeat(array,n-repeat): repetir 2 vezes cada elemento do eixo 0 \n', np.repeat(a,2,axis=0))
print('\nrepeat(array,n-repeat): repetir 2 vezes cada elemento do eixo 1 \n', np.repeat(a,2,axis=1))

a:
 [[1 2]
 [3 4]]

repeat(array,n-repeat): repetir 2 vezes cada elemento do eixo 0 
 [[1 2]
 [1 2]
 [3 4]
 [3 4]]

repeat(array,n-repeat): repetir 2 vezes cada elemento do eixo 1 
 [[1 1 2 2]
 [3 3 4 4]]
```



# Referências

* [Vídeo **muito bom** Python: NumPy Numerical Python Arrays Tutorial](https://www.youtube.com/watch?v=8Mpc9ukltVA&list=PLORrDfZD1hkFD3HcJVoBsQoXf2BmnUt65)
* [Vídeo Python NumPy Tutorial - NumPy Array - Python Tutorial For Beginners - Python Training - Edureka](https://www.youtube.com/watch?v=8JfDAm9y_7s)
* http://www.numpy.org/
* https://docs.scipy.org/doc/numpy/user/quickstart.html
* https://www.datacamp.com/community/tutorials/python-numpy-tutorial
