# Conceitos, definições, e glossário de _AI_ - Inteligência Artificial

## 1. Introdução ##

Neste capítulo separei referências para conceitos, definições e glossário


## 2. Conceitos


### Inteligência Computacional
Inteligência Computacional é uma área bem vasta e bem estabelecida. O uso prático: Netflix, Google, Amazon, WhatsApp corretor ortográfico(processamento de linguagem natural).


### _AI_ Artificial Intelligence (Inteligência Artificial)
A teoria e desenvolvimento de sistemas computacionais capazes de executarem tarefas que normalmente requeriam a inteligêcia humana. Surgiu logo após a 2a guerra mundial


### _ML_ Machine Learning
O campo da ciência que usa técnicas estatísticas para dar aos sistemas computacionais a habilidade de "ler", isto é que progressivamente melhore o desempenho da execução de uma tarefa específica com dados, sem terem sido explicitamente programados para tal.


### _DL_ Deep Learning
É parte do _ML_ Machine Learning que utiliza métodos baseado no aprendizado de dados, diferentemente de tarefas baseadas em algorítimos.

### _AI_ vs _ML_ vs _DL_

![Artificial Intelligence vs Machine Learning vs Deep Learning](ai_vs_ml_vs_dl.png)

### Teste de Turing
O [Teste de Turing](https://pt.wikipedia.org/wiki/Teste_de_Turing) testa a capacidade de uma máquina exibir comportamento inteligente equivalente a um ser humano, ou indistinguível deste.

### DataSet ou conjunto de Dados
Em _AI_, um programa aprende a partir de uma experiências, que pode ser provida por um conjunto de dados. Exemplo: dados de pacientes de um hospital, identificador, nome, idade, peso, temperatura, presença de manchas, etc.  O dado também é chamado de objeto, exemplo, amostra, registro ou padrão.


### Dado imperfeito ou ruído
Quando em um conjunto de treinamento, pelo menos um dos atribudos não está disponível ou é inválido no domínio.


### Tipos de atributos Qualitativo
Um atribuito **qualitativo**, também chamado de simbólico ou categórico, representa qualidade ou seja valores podem ser associados a categorias. Podem ser **ordenados**, porém **operações aritméticas** não podem ser aplicadas.  Ex: nome, sexo, 


### Tipos de atributos Quantitativo
Um atribuito **quantitativo**, também chamado de numérico, ele representa quantidades. Eles podem ser divididos em **contínuos** ou **discretos**. O atributo **quantitativo contínuo** podem assumir número infinito de valores, frequentemente representado por um número real.
ou seja valores podem ser associados a categorias. Podem ser **ordenados**, porém **operações aritméticas** não podem ser aplicadas.  Ex: numero de internações.


### Escalas de atributos
Escala de atribuitos define operações que podem ser aplicadas aos atributos, que podem ser:
* **qualitativo nominais**: Os valores são nomes diferentes e carregam a menor quantidade de informação possível. Não existe relação de ordem entre os valores. As operações aplicáveis são:  `=` **igualdade** ou `!=`**diferança**. Ex: Cor, Sexo, Id
* **qualitativo ordinais**: Os valores refletem ordem das categorias representadas. As operações aplicáveis são: `=`, `!=`, `<`, `<=`, `>`, `>=`. Exemplo: Hierarquia militar, avaliação qualitativa de grande, pequena. 
* **quantitativo racionais**: Os valores tem significado absoluto. As operações aplicáveis são: `+` adição, `-` subtração, `*` multiplicação e `/` divisão, além das operações `=`, `!=`, `<`, `<=`, `>` e `>=`. Exemplos: peso, quantidade de algum atributo.
* **quantitativo intervalares**: Os valores tem significado quantitativo e variam dentro de um intervalo. As operações aplicáveis são: `+` adição, `-` subtração, além das operações `=`, `!=`, `<`, `<=`, `>` e `>=`. Exemplos: Temperatura.


### Tarefas de aprendizado
* **Preditivas**: Encontrar uma função, modelo ou hipótese que pode ser utilizada para prever um rótulo ou valor. Ex: prever o valor de um imóvel ou um rótulo de doente/saudável para um paciente.
* **Descritivas**: Explorar ou descrever um conjunto de dados, pois não possuem saída associada.


### Tipos de aprendizado
!tipos-de-aprendizado.png!
PS: Não é uma subdivisão rígida, mas didatica:
* **Aprendizado Indutivo**: 
* **Aprendizado Supervisionado**: Preditivo, possue um __supervisor externo__. É conhecido a saída desejada para cada exemplo. Ex: situação de um paciente no hosmpital. 
  * **Classificação**: Tem um rótulo discreto. Exemplo: diagnóstico(saudável,doente), bom/mau pagador, etc.
  * **Regressão**: Não tem rótulos discretos, pois eles são contínuos. Exemplo: peso, altura, etc.
* **Aprendizado Não-Supervisionado**: Descritivo.  Os algorítimos não fazem uso de atributos de saída, eles exploram as regularidades nos dados
  * **Sumarização**: Encontrar descrição compacta dos dados.
  * **Associação**: Encontrar padrões frequentes de associações entre atributos.
  * **Agrupamento**: agrupamento por similaridade ou subconjuntos ou cluster.


### Processo de aprendizado supervisionado
No aprendizado supervisionado, o programa é __treinado__ sobre um conjunto de dados pré-definidos. Baseado no treinamento com dados pré-definidos o programa pode tomar decisão para novos dados. Ex: análise de sensibilidade de tweets (positivo ou negativo). O objetivo é a partir do passado, prever o que se segue. 
A **classificação** é uma subcategoria do aprendizado supervisionado, cujo processo consiste em atribuir um rótulo para uma nova amostra.
A **regressão** é uma subcategoria do aprendizado supervisionado, quando o valor tem um espectro contínuo podemos utilizar regressão.


### Processo de aprendizado não-supervisionado
Mesmo com exemplos não rotulados é possível encontrar __padrões__ os padrões existentes dados. Isto é muito usado em uma abordagem chamada __DataMinig__. É possível fazer organização de padrões consistentes nos dados, ou __clustes__. O objetivo é extrair informações relevantes de dados __não rotulados__.


### Processo de aprendizado semi-supervisionado
Utiliza dados rotulados e não rotulados no treinamento. Normalmente uma pequena quantidade de dados rotulado com uma grande quantidade de dados não rotulados (que são obtidos com menos esforço)


### Processo de aprendizado por reforço
O algorítmo aprende por tentativa e erro. 



### Técnicas de aprendizado de máquina
Existe várias técnicas de aprendizado de máquina:
* Redes Neurais
* Árvore de Decisão
* KNN
* K-Means
* Redes Bayesianas
* Máquina de vetor de suporte (SVMs)
* Regressão Linear
Ps: Não existe a **melhor** técnica e sim a mais adequada levando em consideração os dados e tempo de espera


### Clusterização
Processo de agrupar objetos em classes de objetos similares. Cluster é uma coleção de objeto que é similar a outros de acordo com um critério de similiradade.


### Regressão Linear
Em estatística ou econometria, regressão linear é uma equação para se estimar a condicional (valor esperado) de uma variável y, dados os valores de algumas outras variáveis x.

### Regressão Linear Simples
Regressão Linear Simples é quando temos uma única variável explanatória (x).


### Regressão Linear Múltipla
Regressão múltipla é uma coleção de técnicas estatísticas para construir modelos que descrevem de maneira razoável relações entre várias variáveis explicativas de um determinado processo. A diferença entre a regressão linear simples e a múltipla é que na múltipla são tratadas duas ou mais variáveis explicativas.



# Referências

* Vídeo [Inteligência Artificial, Machine Learning e Deep Learning (Exemplos e Diferenças)](https://www.youtube.com/watch?v=5UYpSE3dQSQ&list=PLORrDfZD1hkE-STpneL0hV3_m2tjv0qAq) - Introdutório dos conceitos, mostra a diferença entre AI vs ML vs DL, para não técnicos de forma bastante simples e efetiva
* Vídeo [Robo Leo aprendendo a andar](https://www.youtube.com/watch?v=SBf5-eF-EIw)
* Vídeo [Teste de Turing](https://www.youtube.com/watch?v=WWmblRWRdLc)
* [Fundamentos Data Science](https://jvilar.wordpress.com/2017/01/29/fundamentos-de-data-science-machine-learning-parte-1/)
