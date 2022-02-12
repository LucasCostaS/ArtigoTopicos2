# Naive Bayes

## O que é Naive Bayes?

O algoritmo Naive Bayes é um classificador probabilístico muito utilizado em machine learning. Baseado no [Teorema de Bayes](https://pt.wikipedia.org/wiki/Teorema_de_Bayes), o modelo foi criado por um matemático inglês, e também ministro presibiteriano, chamado Thomas Bayes (1701 – 1761) para tentar provar a existência de Deus.

Atualmente, o algoritmo se tornou popular na área para categorizar textos baseado na frequência das palavras usadas, e assim pode ser usado para identificar se determinado e-mail é um SPAM ou sobre qual assunto se refere determinado texto, por exemplo.

Por ser muito simples e rápido, possui um desempenho relativamente maior do que outros classificadores. Além disso, o Naive Bayes só precisa de um pequeno número de dados de teste para concluir classificações com uma boa precisão.

A principal característica do algoritmo, e também o motivo de receber “naive” (ingênuo) no nome, é que ele desconsidera completamente a correlação entre as variáveis (features). Ou seja, se determinada fruta é considerada uma “Maçã” se ela for “Vermelha”, “Redonda” e possui “aproximadamente 10cm de diâmetro”, o algoritmo não vai levar em consideração a correlação entre esses fatores, tratando cada um de forma independente.

<div>
<img src="https://insightimi.files.wordpress.com/2020/04/unnamed-1.png" width="600">
</div>


## Usos

Frequentemente aplicado em processamento de linguagem natural e diagnósticos médicos, o método pode ser usado quando os atributos que descrevem as instâncias forem condicionalmente independentes. Ou seja, o teorema de Bayes trata sobre probabilidade condicional. Isto é, qual a probabilidade de o evento A ocorrer, dado o evento B.

Um problema simples que exemplifica bem o teorema é o cálculo de probabilidades em cima de diagnóstico de doenças. Imagine que estamos trabalhando no diagnóstico de uma nova doença. Após realizar testes, coletas e análises com 100 pessoas distintas, descobrimos que 20 pessoas possuíam a doença (20%) e 80 pessoas estavam saudáveis (80%).

De todas as pessoas que possuíam a doença, 90% receberam Positivo no teste. Já 30% das pessoas que não possuíam a doença também receberam o teste positivo.

Vamos para a tabulação dos dados:

100 pessoas realizaram o teste.
20% das pessoas que realizaram o teste possuíam a doença.
90% das pessoas que possuíam a doença, receberam positivo no teste.
30% das pessoas que não possuíam a doença, receberam positivo.

A partir destes dados, surge o problema: se uma nova pessoa realizar o teste e receber um resultado positivo, qual a probabilidade dela realmente possuir a doença?

Essa probabilidade a posteriori é resolvida pelo Naive Bayes. Para isso, é preciso multiplicar a probabilidade a priori (possuir a doença) pela probabilidade de “receber um resultado positivo, dado que tem a doença”.

Com esses dados, também podemos calcular a probabilidade a posteriori da negação (não possuir a doença, dado que recebeu um resultado positivo).

## A matemática por trás

Considerando um caso simples em que temos apenas 2 features com 2 valores possíveis {0, 1} cada e nossa label pode ser classificada como {0, 1}, precisamos calcular o seguinte para fazer a tabela de probabilidade:
-P(X1 = 0, X2 = 0 | Y = 0) = ?; P(X1 = 0, X2 = 1 | Y = 0) = ?
-P(X1 = 1, X2 = 0 | Y = 0) = ?; P(X1 = 1, X2 = 1 | Y = 0) = ?
-P(X1 = 0, X2 = 0 | Y = 1) = ?; P(X1 = 0, X2 = 1| Y = 1) = ?
-P(X1 = 1, X2 = 0 | Y = 1) = ?; P(X1 = 1, X2 = 1 | Y = 1) = ?

Cada uma dessas probabilidades será colocada na tabela de probabilidades. A tabela de probabilidade é montada da seguinte maneira:

<div>
<img src="https://miro.medium.com/max/1320/1*pjIsjntowGptS-wQRJJxaA.png" width="600">
</div>

Na prática, devido ao fato de lidarmos com as variáveis X de forma que são independentes duas a duas, temos, por exemplo, que
P(X1 = 0, X2 = 0 | Y = 0) = P(X1 = 0 | Y = 0) * P(X2 = 0 | Y = 0)
E é feito o mesmo procedimento de forma análoga às demais probabilidades enunciadas acima. Isso diminui o número de probabilidades que precisamos calcular, principalmente quando o número de features e valores possíveis aumenta.
Para a implementação desse modelo, temos 3 tipos de algoritmos Naive Bayes mais usados, os quais daremos mais detalhes. Cada algoritmo funcionará para calcular o P(x<sub>i</sub> | y) de modo que as features de cada observação estejam de acordo com um tipo de distribuição de probabilidade especificado pelo algoritmo escolhido.

### Gaussian Naive Bayes

Nesse primeiro algoritmo, P(x<sub>i</sub> | y) é dado por:
<div>
<img src="https://miro.medium.com/max/922/1*8E4UHoapCFCpTf79RA2NiA.png" width="600">
</div>

A média (μy) é o valor médio de x<sub>i</sub>, considerando as observações de classe y. E o desvio padrão (σy) é o desvio padrão da feature x<sub>i</sub>, considerando as observações da classe y.

### Multinomial Naive Bayes

Esse algoritmo usa os dados em uma distribuição multinomial, que é uma generalização da distribuição binomial. Essa distribuição é parametrizada por vetores θ<sub>yi</sub>=(θ<sub>y1</sub>,…,θ<sub>yn</sub>), θ<sub>yi</sub> é a probabilidade do evento i ocorrer, dado que a classe é y. Podemos dizer que cada vetor θ<sub>y</sub> representa uma observação e n é o número de features. Assim, θ<sub>yi</sub> = P(x<sub>i</sub> | y) e é estimado pela seguinte fórmula:
<div>
<img src="https://miro.medium.com/max/296/1*DqNybCxq5P4O0wWRnMhDNw.png" width="400">
</div>

N<sub>yi</sub> é o número de vezes que a feature x<sub>i</sub> aparece no conjunto de treinamento, N<sub>y</sub> é o número de observações com classe y, n é o número de features e alfa é uma constante que contabiliza os recursos que não estão presentes nas amostras de aprendizado e impede que haja probabilidade igual a 0. Se alfa = 1, ele é chamado de Laplace smoothing e, se alfa > 1, é chamado Lidstone smoothing. Se alfa = 0, não há correção.

Para podermos visualizar mais facilmente a necessidade, em alguns casos, da correção, digamos que temos a seguinte tabela de probabilidade:
<div>
<img src="https://miro.medium.com/max/1400/1*ELFO8xWfna-2QjJthdk7DA.png" width="800">
</div>

Se tentarmos classificar o caso em que X = (income = alta, age = >30 e <60, loan = medio), podemos perceber que:
-P(Y = 0 | X = (income = alta, age = >30 e <60, loan = medio) = 0
-P(Y = 1 | X = (income = alta, age = >30 e <60, loan = medio) = 0

Assim, é necessário fazer um [additive smoothing](https://en.wikipedia.org/wiki/Additive_smoothing) (que pode ser Laplace smoothing ou Lidstone smoothing), que é uma correção que consiste em adicionar dados à base de treinamento para que não haja probabilidades iguais a 0. Tal processo é parametrizado pelo alfa.

### Bernoulli Naive Bayes

Esse algoritmo se baseia numa base de dados de acordo com a Distribuição Multivariada de Bernoulli, que é composta por diversas features, as quais são valores binários, ou seja, podem assumir um valor dentre dois valores possíveis.
Se alguma feature não for composta por valores binários, BernoulliNB() irá transformá-la em uma feature composta por valores binários dependendo do parâmetro binarize.
Nesse modelo, o P(x<sub>i</sub> | y) é dado por:
<div>
<img src=https://miro.medium.com/max/874/1*pDu3m0VKLvpATn1lEdAvUQ.png" width="600">
</div>

P(i | y) é o parâmetro p da distribuição de Bernoulli. Assim, P(i | y) = p se y = True, e P(i | y) = 1-p se y = False.

Repare que, ao contrário do Multinomial Naive Bayes, há uma penalidade no caso de não ocorrência da feature i.

## Vantagens e Desvantagens

### Vantagens

-Esse algoritmo funciona rapidamente e pode economizar muito tempo.
-Naive Bayes é adequado para resolver problemas de previsão multiclasse.
-Se sua suposição de independência de recursos for verdadeira, ele pode ter um desempenho melhor do que outros modelos e requer muito menos dados de treinamento.
-Naive Bayes é mais adequado para variáveis ​​de entrada categóricas do que para variáveis ​​numéricas.

### Desvantagens

-Naive Bayes assume que todos os preditores (ou recursos) são independentes, raramente acontecendo na vida real. Isso limita a aplicabilidade desse algoritmo em casos de uso do mundo real.
-Este algoritmo enfrenta o "problema de frequência zero", onde atribui probabilidade zero a uma variável categórica cuja categoria no conjunto de dados de teste não estava disponível no conjunto de dados de treinamento. Seria melhor se você usasse uma técnica de suavização para superar esse problema.
-Suas estimativas podem estar erradas em alguns casos, então você não deve levar suas saídas de probabilidade muito a sério.
