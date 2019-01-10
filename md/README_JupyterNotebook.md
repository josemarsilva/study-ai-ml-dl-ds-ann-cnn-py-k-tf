# Jupyter Notebook

# 1. Introdução

Neste capítulo separei referências para o Jupyter Notebook.

## 2. Documentação

## 2.1. Guia de Instalação

* Faça o download do Python 3.x.x de https://www.python.org/downloads/ e instale
* Instale o Jupyter Notebook pelo Pip3

```cmd
pip3 install jupyter
```


## 2.2. Guia de Uso

### 2.2.1. Inciar o Jupyter Notebook ###

* Inicie o Jupyter Notebook

```cmd
C:\...\> jupyter-notebook
```

```txt
[I 16:55:51.532 NotebookApp] JupyterLab extension loaded from C:\ProgramData\Anaconda3\lib\site-packages\jupyterlab
[I 16:55:51.532 NotebookApp] JupyterLab application directory is C:\ProgramData\Anaconda3\share\jupyter\lab
[I 16:55:51.672 NotebookApp] Serving notebooks from local directory: C:\Users\Inmetrics
[I 16:55:51.672 NotebookApp] The Jupyter Notebook is running at:
[I 16:55:51.672 NotebookApp] http://localhost:8888/?token=a08bf085d6abaebb251f808dcda09463d85633c1f316a126
[I 16:55:51.672 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 16:55:51.790 NotebookApp]
```

* Abra no browser o endereço informado 
```browser
http://localhost:8888/?token=a08bf085d6abaebb251f808dcda09463d85633c1f316a126
```


### 2.2.2. Criar e salvar um novo notebook

* Clique no botão lateral direito "New" em seguida "Python3 (notebook)" e uma nova instância do browser será aberta para seu Notebook
* Ao lado do prompt `In [ ] `, escreva uma expressão. Exemplo: `1 + 1` e clique em <Ctrl> + <Enter> para avaliar o resultado. A resposta será `2`.
* Você pode escrever trechos de programas Python e o JupyterNotebook avalia a resposta 
* Para salvar o arquivo com o seu notebook, pela opção de menu `File | Save As` ou pelo botão com o ícone de salvar, informe o nome do arquivo. Ou também clicando sobre o título do notebook, você pode renomeá-lo. Um arquivo de mesmo nome e extensão (.ipynb) será cliado. Exemplo: `Step-01.ipynb`


### 2.2.3. Mostrar uma imagem em seu notebook
```ipynb
from IPython.display import Image
from IPython.core.display import HTML
Image(url="python-logo.jpg")
```

### 2.2.4. Expressões

```ipynb
10 * 4
^ENTER
40
```

```ipynb
4 * "Hello"
^ENTER
HelloHelloHelloHello
```

* Consulte o gabarito em [Exercicio-01-01.ipynb](src/ipynb/01-JupyterNotebook/Exercicio-01.ipynb)



# Referências

* [Jupyter Notebook - Org](https://jupyter.org/)
* [Curso Python 3 | Aula 1 - Notebook Jupyter](https://www.youtube.com/watch?v=m0FbNlhNyQ8)
* [Getting Started With Jupyter Notebook for Python](https://www.youtube.com/watch?v=CwFq3YDU6_Y)
* [Tutorial do Notebook Jupyter: Introdução, Configuração e Passo a Passo](https://www.youtube.com/watch?v=HW29067qVWk&t=72s)
