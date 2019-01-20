# README Python DataSet Manipulation

## 1. Introdução ##
O objetivo deste documento é ensinar a manipulação de DataSet em Python.


## 2. Guia de Aprendizado

## 2.1. Repositórios de DataSet
Você pode encontrar dados em DataSet em diversos lugares, sites especializados, sites do governo, etc. Segue alguns exemplos:

* https://archive.ics.uci.edu/ml/datasets.html


## 2.2. Explorando Iris DataSet
Em [Iris DataSet](https://archive.ics.uci.edu/ml/datasets/Iris) você tem o DataSet disponível para download. É um DataSet muito famoso e bastante utilizado para fins didáticos. Observe que são 50 dados (instâncias) com 4 attributos, sem valores faltantes.

* Faça o download do arquivo `iris.data` e organize dentro de uma pasta junto com o Jupyter-Notebook
* O layout descritivo do arquivo encontra-se na página do DataSet, ie (1.comprimento da sépala; 2.largura da sépala; 3.comprimento da pétala; 4. largura da pétala; 5. Classe (Iris Setosa; Iris Versicolor; Iris Virgínica)
* Esta é uma amostra das 3 primeiras linhas do arquivo `iris.data`:

```txt
5.1,3.5,1.4,0.2,Iris-setosa
4.9,3.0,1.4,0.2,Iris-setosa
4.7,3.2,1.3,0.2,Iris-setosa
```

* Primeiramente vamos ler o arquivo todo e jogá-lo em uma estrutura de memória do Python para fazermos algumas operações. Premissa: o arquivo `iris.data` encontra-se na pasta `data` tem 152 linhas, porém as últimas duas linhas são vazias.

```ipynb
with open('data/iris.data', 'r') as file: 
    lista = file.read().splitlines()
    print('n-length: ', len(lista))
    print('  0: ', lista[0])
    print('  1: ', lista[1])
    print('  2: ', lista[2])
    print('  :    :')
    print('%s: %s' % ( len(lista)-1, lista[len(lista)-3] ))
    print('%s: %s' % ( len(lista)-2, lista[len(lista)-2] ))
    print('%s: %s' % ( len(lista)-1, lista[len(lista)-1] ))
```

```txt
n-length:  151
  0:  5.1,3.5,1.4,0.2,Iris-setosa
  1:  4.9,3.0,1.4,0.2,Iris-setosa
  2:  4.7,3.2,1.3,0.2,Iris-setosa
  :    :
150: 6.2,3.4,5.4,2.3,Iris-virginica
149: 5.9,3.0,5.1,1.8,Iris-virginica
150: 
```

* Vamos limpar as linhas vazias no final do arquivo.

```ipynb
ult_item_removido =  lista.pop()
print('Novo tamanho n-length: ', len(lista))
```

```txt
Novo tamanho n-length:  149
```

* Vamos descobrir o menor e o maior valor para: sepal-length, sepal-width, petal-length, petal-width

```ipynb
idxSepalLength = 0
idxSepalWidth = 1
idxPetalLength = 2
idxPetalWidth = 3
sepal_max_length = float(-9999999999)
sepal_min_length = float( 9999999999)
sepal_max_width = float(-9999999999)
sepal_min_width = float( 9999999999)
petal_max_length = float(-9999999999)
petal_min_length = float( 9999999999)
petal_max_width = float(-9999999999)
petal_min_width = float( 9999999999)

for item in lista:
    
    if float(item.split(',')[idxSepalLength]) > sepal_max_length:
        sepal_max_length = float(item.split(',')[idxSepalLength])
    if float(item.split(',')[idxSepalLength]) < sepal_min_length:
        sepal_min_length = float(item.split(',')[idxSepalLength])
        
    if float(item.split(',')[idxPetalLength]) > petal_max_length:
        petal_max_length = float(item.split(',')[idxPetalLength])
    if float(item.split(',')[idxPetalLength]) < petal_min_length:
        petal_min_length = float(item.split(',')[idxPetalLength])

    if float(item.split(',')[idxSepalWidth]) > sepal_max_width:
        sepal_max_width = float(item.split(',')[idxSepalWidth])
    if float(item.split(',')[idxSepalWidth]) < sepal_min_width:
        sepal_min_width = float(item.split(',')[idxSepalWidth])
        
    if float(item.split(',')[idxPetalWidth]) > petal_max_width:
        petal_max_width = float(item.split(',')[idxPetalWidth])
    if float(item.split(',')[idxPetalWidth]) < petal_min_width:
        petal_min_width = float(item.split(',')[idxPetalWidth])


print('        +---------------------+---------------------+')
print('        |        length       |        width        |')
print('        +----------+----------+----------+----------+')
print('        |  min()   |  max()   |  min()   |  max()   |')
print('+-------+----------+----------+----------+----------+')
print('| Sepal | %f | %f | %f | %f |' % (sepal_min_length, sepal_max_length, sepal_min_width, sepal_max_width))
print('| Petal | %f | %f | %f | %f |' % (petal_min_length, petal_max_length, petal_min_width, petal_max_width))
print('+-------+----------+----------+----------+----------+')
```

```txt
        +---------------------+---------------------+
        |        length       |        width        |
        +----------+----------+----------+----------+
        |  min()   |  max()   |  min()   |  max()   |
+-------+----------+----------+----------+----------+
| Sepal | 4.300000 | 7.900000 | 2.000000 | 4.400000 |
| Petal | 1.000000 | 6.900000 | 0.100000 | 2.500000 |
+-------+----------+----------+----------+----------+
```


# Referências

