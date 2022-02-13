# Floresta Aleatoria

## O que é Floresta Aleatoria?

Floresta Aleatória (Random Forest) é um algoritmo de aprendizagem de máquina flexível e fácil de usar que produz excelentes resultados a maioria das vezes, mesmo sem ajuste de hiperparâmetros. É também um dos algoritmos mais utilizados, devido à sua simplicidade e o fato de que pode ser utilizado para tarefas de classificação e também de regressão.

É um algoritmo de aprendizagem supervisionada. Como você pode perceber pelo seu nome, ele cria uma floresta de um modo aleatório. A “floresta” que ele cria é uma combinação ([ensemble](https://medium.com/dados-e-saude/machine-learning-e-ensembles-780f3a8aa36d)) de árvores de decisão, na maioria dos casos treinados com o método de bagging. A idéia principal do método de bagging é que a combinação dos modelos de aprendizado aumenta o resultado geral.

## Usos

O algorimo Floresta Aleatória é utilizado em muitas áreas diferentes, tal como setor bancário, mercado financeiro, medicina, comércio eletrônico. No setor bancário ele é utilizado, por exemplo, para detectar clientes que irão utilizar os serviços bancários mais frequentemente que outros e pagar suas dívidas pontualmente. Neste domínio ele também é utilizado para detectar fraudes de clientes que querem lesar o banco. No setor financeiro, ele é utilizado para determinar o desempenho futuro de uma ação. Na área de saúde ele é utilizado para identificar a correta combinação de componentes em medicina, e também é utilizado para analisar o histórico médico de um paciente para identificar doenças. Por último, em comércio eletrônico o Floresta Aleatória é utilizado para determinar se um cliente irá gostar do produto ou não.

## A matemática por trás

O algoritmo de treinamento para florestas aleatórias aplica a técnica geral de agregação de bootstrap , ou ensacamento, para alunos de árvore. Dado um conjunto de treinamento X = x<sub>1</sub> , ..., x<sub>n</sub> com respostas Y = y<sub>1</sub> , ..., y<sub>n</sub> , ensacamento repetidamente ( B vezes) seleciona uma amostra aleatória com substituição do conjunto de treinamento e ajusta as árvores a estes amostras:

Para b = 1, ..., B :
1. Amostra, com substituição, n exemplos de treinamento de X , Y ; chame-os de X<sub>b</sub> , Y<sub>b</sub> .
2. Treine uma árvore de classificação ou regressão f<sub>b</sub> em X<sub>b</sub> , Y<sub>b</sub> .

Após o treinamento, as previsões para amostras não vistas x' podem ser feitas calculando a média das previsões de todas as árvores de regressão individuais em x' :

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/b54befce12aefdb29442bfc71cb5ad452364e8d8" width="300">
</div>

ou tomando a maioria dos votos no caso de árvores de classificação.

Este procedimento de bootstrapping leva a um melhor desempenho do modelo porque diminui a variância do modelo, sem aumentar o viés. Isso significa que, embora as previsões de uma única árvore sejam altamente sensíveis ao ruído em seu conjunto de treinamento, a média de muitas árvores não é, contanto que as árvores não sejam correlacionadas. Simplesmente treinar muitas árvores em um único conjunto de treinamento forneceria árvores fortemente correlacionadas (ou até mesmo a mesma árvore muitas vezes, se o algoritmo de treinamento for determinístico); a amostragem bootstrap é uma forma de descorrelacionar as árvores, mostrando-lhes diferentes conjuntos de treinamento.

Além disso, uma estimativa da incerteza da previsão pode ser feita como o desvio padrão das previsões de todas as árvores de regressão individuais em x' :

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/11e64a440f8625c492d848b38785f833a5882432" width="300">
</div>

O número de amostras / árvores, B , é um parâmetro livre. Normalmente, algumas centenas a vários milhares de árvores são usadas, dependendo do tamanho e da natureza do conjunto de treinamento. Um número ideal de árvores B pode ser encontrado usando validação cruzada ou observando o erro fora do saco : o erro médio de predição em cada amostra de treinamento x<sub>i</sub> , usando apenas as árvores que não tinham x<sub>i</sub> em sua amostra de bootstrap. O treinamento e o erro de teste tendem a se estabilizar depois que algumas árvores foram ajustadas.

## Vantagens e Desvantagens

### Vantagens

Uma das vantagens do Floresta Aleatória é que ele pode ser utilizado tanto para regressão quanto para classificação e é fácil visualizar a importância relativa que ele atribui para cada característica na suas entradas.

O Floresta Aleatória é também considerado um algoritmo muito fácil e acessível, pois seus hiperparâmetros com valores default geralmente produzem um bom resultado de predição. O número de hiperparâmetros não é tão grande e são muito fáceis de compreender.

### Desvantagens

Um dos grande problemas em aprendizagem de máquina é subreajuste (overfitting), mas a maior parte do tempo isto não ocorrerá tão facilmente com um classificador de Floresta Aleatória qualquer. Isto porquê, se há árvores suficiente na floresta, o classificador não irá sobreajustar o modelo.

A maior limitação do Floresta Aleatória é que uma quantidade grande de árvores pode tornar o algoritmo lento e ineficiente para predições em tempo real. Em geral, estes algoritmos são rápidos para treinar, mas muito lentos para fazer predições depois de treinados. Uma predição com mais acurácia requer mais árvores, o que faz o modelo ficar mais lento. Em muitas aplicações do mundo real o Floresta Alatória é rápido o suficiente, mas pode certamente haver situações onde a performance em tempo de execução é importante e outras abordagens são mais apropriadas.

E é claro, o Floresta Aleatória é uma ferramenta de modelagem preditiva e não descritiva. Isto significa que, se você está procurando uma descrição dos relacionamentos nos seus dados, você deve escolher outras abordagens.
