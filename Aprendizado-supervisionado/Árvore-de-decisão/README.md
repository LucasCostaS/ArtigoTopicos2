# Árvore de decisão

## O que é Árvore de decisão?

Uma árvore de decisão é um algoritmo de aprendizado de máquina supervisionado que é utilizado para classificação e para regressão. Isto é, pode ser usado para prever categorias discretas (sim ou não, por exemplo) e para prever valores numéricos (o valor do lucro em reais).

Assim como um fluxograma, a árvore de decisão estabelece nós (decision nodes) que se relacionam entre si por uma hierarquia. Existe o nó-raiz (root node), que é o mais importante, e os nós-folha (leaf nodes), que são os resultados finais. No contexto de machine learning, o raiz é um dos atributos da base de dados e o nó-folha é a classe ou o valor que será gerado como resposta.

<div>
<img src="https://miro.medium.com/max/1400/0*Wy3QjtXL9qf-Ssyz.jpg" width="1000">
</div>

Na ligação entre nós, temos regras de “se-então”. Ao chegar em um nó A, o algoritmo se pergunta acerca de uma regra, uma condição, como “se a característica X do registro analisado é menor do que 15?”. Se for menor, então ele vai para um lado da árvore; se for maior, então ele vai para outro. No próximo nó, segue a mesma lógica.

É um algoritmo que segue o que chamamos de “recursivo” em computação. Ou seja, ele repete o mesmo padrão sempre na medida em que vai entrando em novos níveis de profundidade. É como se uma função chamasse a ela mesma como uma segunda função para uma execução paralela, da qual a primeira função depende para gerar sua resposta.

## Usos

As árvores servem para classificação ou regressão, ambos tipos de tarefas de aprendizado supervisionado. Aliás, essa versatilidade explica muito do sucesso desse algoritmo, principalmente se comparado com outros mais simples, como o [Naive-Bayes](Naive-Bayes).

Outra aplicação muito importante das árvores é quando há um problema de diversos rótulos. Ou seja, quando as categorias de classificação são múltiplas, e não apenas duas (como sim ou não). Outros algoritmos apresentam consideráveis problemas e uma maior complexidade, ao passo que com as árvores, cientistas de dados conseguem lidar com isso com facilidade.

Além disso, quando é preciso lidar com dados sem se preocupar muito com o tratamento deles, a decision tree cai bem como uma luva.

Nela, valores que ficam muito fora do padrão dos dados ou valores faltantes não chegam a ser prejudiciais. Pouquíssimas etapas de tratamento são necessárias. A pessoa cientista não precisará nem mesmo converter os dados para informações numéricas, já que esse algoritmo também lida bem com informações categóricas (nominais).

Em casos de problemas gerais que envolvem tanto classificação quanto regressão, as árvores também são uma boa pedida. Nesse caso, pode-se implementar uma random forest (floresta aleatória), que consiste basicamente em um conjunto de árvores treinadas que oferecem uma predição sobre os dados, escolhendo uma categoria.

Então, é feita uma avaliação da categoria que mais apareceu nos resultados das árvores para que haja uma decisão final.

### Exemplos

**Diagnóstico de doenças**

Uma decision tree pode ser aplicada para identificar doenças a partir de informações cedidas ao algoritmo como treinamento — uma classificação. Nesse caso, o sistema apreende os dados, entende suas relações, realiza os cálculos a fim de entender quais são os nós mais importantes e ajusta as condições.

A grande vantagem, como falamos, é o fato de que não é necessário se preocupar muito com o tratamento dos dados. Para resultados ainda mais interessantes, uma assembleia (random forest) deve ser adotada.

**Previsão de empréstimo**

Outro tipo de uso é para previsão de um valor de empréstimo que pode ser concedido a um usuário do banco. Esse é um problema de regressão, pois requer uma informação numérica como saída. O sistema vai entender como a base de dados está organizada de acordo com os atributos e criar um modelo capaz de fazer essa previsão.

**Análise de sentimentos**

Não é incomum ver também aplicações na área da análise de sentimentos, subcategoria do campo de processamento de linguagem natural. O modelo entende os dados e tenta prever se um texto deve ser categorizado como positivo ou negativo, por exemplo. Para melhores resultados, a random forest é aplicada também.

**Previsão de saída de funcionários**

Outro uso muito específico é para o RH saber quando um funcionário está quase saindo da empresa por insatisfação. Com a análise de dados sobre cada um, o modelo entende a base de dados e consegue realizar uma predição, ou seja, uma classificação.

## A matemática por trás

Nós estamos interessados em encontrar a melhor divisão em termos de alguma medida de impureza, tal como Gini Index, Entropia ou taxa de erro. Encontrar o ponto de corte que leva a árvore de decisão ótima pode ser computacionalmente inviável (construir a árvore de decisão binária ótima é um problema np-completo). Portanto, nós nos contentamos em fazer escolhas locais ótimas (não garantindo o ótimo global) para encontrar o melhor atributo e limiar para o particionamento.

Para encontrar melhor ponto de corte, nós temos de testar todos os possíveis, ou seja, para cada atributo e valores possíveis calcular o ganho de informação (quão pura a divisão torna o espaço) para cada um dos pontos de corte candidatos. Após essa etapa, nós escolhemos o candidato com maior ganho de informação para ser o ponto de corte do nó em questão.

O ganho de informação, de grosso modo, representa a informação aprendida sobre os rótulos quando dividimos uma região do espaço em duas sub-regiões de acordo com ponto de corte. E é definida pela fórmula:

InfoGain(R, R_e, R_d) = H(R) - (|R_e|*H(R_e) + |R_d|*H(R_d)) / |R|

onde H é a impureza da região, R é a região atual, R_e é sub-região da esquerda, R_d é sub-região da direita e |.| é quantidade de exemplos na dada região. Os critérios de impureza mais comuns para classificação são a Entropia e o índice Gini, definidos a seguir:

entropia(R) = -∑ p(c|R) log (p(c|R))

gini(R) = ∑ p(c|R) (1 - p(c|R))

onde p(c|R) é a probabilidade de um ponto da região R pertencer a classe c. Essa probabilidade é estimada pela razão entre quantidade de pontos da classe c e o total de pontos em R.

## Vantagens e Desvantagens

### Vantagens

- Interpretação
  - Percebe-se a razão da decisão
- Facilidade em lidar com diversos tipos de informação
  - Real, nominal, ordinal, etc
  - Não é necessário definir “importância relativa”
- Insensível a factores de escala
- Escolha automática dos atributos mais relevantes em cada caso
  - Atributos mais relevantes aparecem mais acima na árvore
- Adaptável também a problemas de regressão
  - Modelos locais lineares como folhas

### Desvantagens

- Fronteiras lineares e perpendiculares aos eixos
- Sensibilidade a pequenas perturbações no conjunto de treino (geram redes muito diferentes)

## Exemplo de uma aplicação em Python

### Exemplo de um problema de classificação

```Python
from sklearn.datasets import load_iris
from sklearn import tree
iris = load_iris()
X, y = iris.data, iris.target
clf = tree.DecisionTreeClassifier()
clf = clf.fit(X, y)
```

### Exemplo de um problema de regressão

```Python
# Import the necessary modules and libraries
import numpy as np
from sklearn.tree import DecisionTreeRegressor
import matplotlib.pyplot as plt

# Create a random dataset
rng = np.random.RandomState(1)
X = np.sort(5 * rng.rand(80, 1), axis=0)
y = np.sin(X).ravel()
y[::5] += 3 * (0.5 - rng.rand(16))

# Fit regression model
regr_1 = DecisionTreeRegressor(max_depth=2)
regr_2 = DecisionTreeRegressor(max_depth=5)
regr_1.fit(X, y)
regr_2.fit(X, y)

# Predict
X_test = np.arange(0.0, 5.0, 0.01)[:, np.newaxis]
y_1 = regr_1.predict(X_test)
y_2 = regr_2.predict(X_test)

# Plot the results
plt.figure()
plt.scatter(X, y, s=20, edgecolor="black", c="darkorange", label="data")
plt.plot(X_test, y_1, color="cornflowerblue", label="max_depth=2", linewidth=2)
plt.plot(X_test, y_2, color="yellowgreen", label="max_depth=5", linewidth=2)
plt.xlabel("data")
plt.ylabel("target")
plt.title("Decision Tree Regression")
plt.legend()
plt.show()
```
