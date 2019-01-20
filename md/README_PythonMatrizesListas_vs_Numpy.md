# README Python Matrizes com Listas e NumPy

## 1. Introdução ##
O objetivo deste documento é exercitar o conceito de **matriz(( em Python, seja com **Listas aninhadas** ou **NumPy**.


## 2. Guia de Uso

* Jupyter-Notebook deste exercício disponível [PythonMatrizesListas_vs_Numpy.ipynb](../src/ipynb/04-PythonNumPy/PythonMatrizesListas_vs_Numpy.ipynb)

## 2.1. Matrizes e Listas com NumPy
* Matriz é como se fosse uma tabela de "n" por "m" elementos
* Há varias tipos de matriz: quadradas, transpotas, identidade, etc
* Dado a matriz 3x3 abaixo

```txt
| 5  4  7 |
| 0  3  4 |
| 0  0  6 |
```

* Em Python, uma matriz pode ser representada por uma lista de listas (listas aninhadas)

```ipynb
mat = [[5,4,7],[0,3,4],[0,0,6]]
print('mat:\n', mat)
print('mat[0] - Primeira linha da matriz:\n', mat[0])
print('mat[1,1] - Elemento na segunda linha e segunda coluna:\n', mat[1][1])
```

```txt
mat:
 [[5, 4, 7], [0, 3, 4], [0, 0, 6]]
mat[0] - Primeira linha da matriz:
 [5, 4, 7]
mat[1,1] - Elemento na segunda linha e segunda coluna:
 3
```


## 2.2. Obtendo elementos de uma coluna da matriz
* Utilizando **Listas em Python**, para se obter os elementos por coluna é preciso iterar a lista

```ipynb
for linha in mat:
    print(linha[1]) # segunda linha indice = 1
```

```txt
4
3
0
```

* Utilizando NumPy em Python para se obter os elementos da coluna é bem mais simples

```ipynb
import numpy as np
m1 = np.array([[5,4,7],[0,3,4],[0,0,6]])
print('m1:\n', m1)
print('m1[0] - Primeira linha com NumPy Array:\n', m1[0])
print('m1[1,1] - Elemento na segunda linha e segunda coluna:\n', m1[1][1])
print('m1[0] - Primeira linha com NumPy Array:\n', m1[0])
print('m1[0,:] - Primeira linha com NumPy Array (opção 2):\n', m1[0,:])
print('m1[:,1] - Segunda coluna com NumPy Array:\n', m1[:,1])
```

```txt
m1:
 [[5 4 7]
 [0 3 4]
 [0 0 6]]
m1[0] - Primeira linha com NumPy Array:
 [5 4 7]
m1[1,1] - Elemento na segunda linha e segunda coluna:
 3
m1[0] - Primeira linha com NumPy Array:
 [5 4 7]
m1[0,:] - Primeira linha com NumPy Array (opção 2):
 [5 4 7]
m1[:,1] - Segunda coluna com NumPy Array:
 [4 3 0]
```


## 2.3. Construindo uma matriz com geração automática de dados uniforme (arange()) NumPy Array

* NumPy oferece a funcao `arange()` para geração de dados uniformimente espaçados

```ipynb
import numpy as np
m2 = np.arange(0,20) # Criar um array com 20 valores, iniciando em 0, até (20-1)
print('m2:\n', m2)
m3 = np.arange(0,20,4) # criar um array com 20 valores, iniciando em 0, até (20-1), saltando de 4 em 4
print('m3:\n', m3)
```

```txt
m2:
 [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19]
m3:
 [ 0  4  8 12 16]
```


## 2.4. Remodelando (reshape) uma matriz com NumPy Array
* Remodelar uma matriz com NumPy é alterar a estrutura de tamanho dela
* O NumPy é muito eficiente para operações com matrizes
* Mesmo remodelada para uma matriz, é possível pegar o n-ésimo elemento como se fosse um array
* A estrutrua de matriz em NumPy é flexível a ponto de guardar na estrutura tipo de dados diferentes

```ipynb
import numpy as np
m4 = np.reshape(m2, (5,4)) # transforma um array unidimensional em uma matriz 5 x 4
print('m4:\n', m4)
print('m4.item(5):\n', m4.item(5))

l1 = ['python', 'é', 'legal']
l2 = [ 'guido', 'van', 'rossum'] # criador da linguagem Python
l3 = [ 1, 2, 3]

m5 = np.array([l1, l2, l3]) #
print('m5:\n', m5)
```

```txt
m4:
 [[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]
 [12 13 14 15]
 [16 17 18 19]]
m4.item(5):
 5
m5:
 [['python' 'é' 'legal']
 ['guido' 'van' 'rossum']
 ['1' '2' '3']]
```





# Referências

* [Vídeo **muito bom** Python: NumPy Numerical Python Arrays Tutorial](https://www.youtube.com/watch?v=8Mpc9ukltVA&list=PLORrDfZD1hkFD3HcJVoBsQoXf2BmnUt65)
* [Vídeo Python NumPy Tutorial - NumPy Array - Python Tutorial For Beginners - Python Training - Edureka](https://www.youtube.com/watch?v=8JfDAm9y_7s)
* http://www.numpy.org/
* https://www.datacamp.com/community/tutorials/python-numpy-tutorial
* https://docs.scipy.org/doc/numpy/user/quickstart.html