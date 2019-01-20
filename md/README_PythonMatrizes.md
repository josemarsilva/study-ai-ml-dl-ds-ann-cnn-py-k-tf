# README Python Matrizes

## 1. Introdução ##
O objetivo deste documento é exercitar as operações com **matriz** em Python.


## 2. Guia de Uso

* Jupyter-Notebook deste exercício disponível [PythonOperacoesComMatrizes.ipynb](../src/ipynb/04-PythonNumPy/PythonOperacoesComMatrizes.ipynb)

## 2.1. Operações com matrizes
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
```



# Referências

* [Vídeo **muito bom** Python: NumPy Numerical Python Arrays Tutorial](https://www.youtube.com/watch?v=8Mpc9ukltVA&list=PLORrDfZD1hkFD3HcJVoBsQoXf2BmnUt65)
* [Vídeo Python NumPy Tutorial - NumPy Array - Python Tutorial For Beginners - Python Training - Edureka](https://www.youtube.com/watch?v=8JfDAm9y_7s)
* http://www.numpy.org/
* https://www.datacamp.com/community/tutorials/python-numpy-tutorial
* https://docs.scipy.org/doc/numpy/user/quickstart.html