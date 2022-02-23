# O agrupamento difuso

## O que é o metodo fuzzy clustering (agrupamento difuso)?

Tambem chamado de soft clustering, o Fuzzy clustering consiste em metodos onde cada elemento pode pertencer a mais de um agrupamento. Na atualidade o algoritimo de fusszy clustering mais ultilizado é o Fuzzy C-Means (FCM) que é uma adaptação do metodo K-Means a logica difusa, este metodo consiste em escolher um numero C de agrupamentos e para cada ponto de dados calcular um coeficiente para que esteja ou nao relacionado a esses agrupamentos.

## A matemática por trás

Assim como no metodo K-Means Clustering o FCM consiste em definiar para cada agrupamento C um centroide e assim calcular um coeficiente para cada dado relacionando-os aos agrupamentos.

- Calculo do centroide :

Qualquer ponto x tem um conjunto de coeficientes que dão o grau do k-ésimo cluster wk(x). Com o fuzzy c-means, o centroide de um cluster será a média de todos os pontos ponderados pelo grau de pertencimento ao cluster

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/c2f8602b082a7e8bd7d51b83bdb328898be77763" width="300">
</div>

Onde m é o hiperparâmetro que controla quão difuso será o cluster. Quanto maior for, mais difuso será o cluster no final.

- Metodo

O algoritmo FCM tenta particionar uma coleção finita de {\displaystyle n}n elementos {\displaystyle X=\{\mathbf {x} _{1},...,\mathbf {x} _{n}\}}{\displaystyle X=\{\mathbf {x} _{1},...,\mathbf {x} _{n}\}} em uma coleção de c clusters difusos, respeitando algum critério determinado.

Dado um conjunto finito de dados, o algoritimo retorna uma lista de {\displaystyle c}c centros de cluster {\displaystyle C=\{\mathbf {c} _{1},...,\mathbf {c} _{c}\}}{\displaystyle C=\{\mathbf {c} _{1},...,\mathbf {c} _{c}\}} e uma matriz de partição

{\displaystyle W=w*{i,j}\in [0,1],\;i=1,...,n,\;j=1,...,c}{\displaystyle W=w*{i,j}\in [0,1],\;i=1,...,n,\;j=1,...,c}, onde cada elemento, {\displaystyle w*{ij}}{\displaystyle w*{ij}} , diz o grau que o elemento {\displaystyle \mathbf {x} _{i}}{\displaystyle \mathbf {x} _{i}} pertence ao cluster {\displaystyle \mathbf {c} _{j}}{\displaystyle \mathbf {c} _{j}}.

O FCM visa minimizar uma função objetiva:

{\displaystyle {\underset {C}{\operatorname {arg\,min} }}\sum _{i=1}^{n}\sum _{j=1}^{c}w*{ij}^{m}\left|\mathbf {x} *{i}-\mathbf {c} _{j}\right\|^{2},}{\displaystyle {\underset {C}{\operatorname {arg\,min} }}\sum _{i=1}^{n}\sum _{j=1}^{c}w_{ij}^{m}\left|\mathbf {x} _{i}-\mathbf {c} _{j}\right\|^{2},}
onde:

{\displaystyle w*{ij}={\frac {1}{\sum *{k=1}^{c}\left({\frac {\left\|\mathbf {x} _{i}-\mathbf {c} _{j}\right\|}{\left\|\mathbf {x} _{i}-\mathbf {c} _{k}\right\|}}\right)^{\frac {2}{m-1}}}}.}{\displaystyle w*{ij}={\frac {1}{\sum *{k=1}^{c}\left({\frac {\left\|\mathbf {x} _{i}-\mathbf {c} _{j}\right\|}{\left\|\mathbf {x} _{i}-\mathbf {c} _{k}\right\|}}\right)^{\frac {2}{m-1}}}}.}

## Vantagens e Desvantagens

### Vantagens

### Desvantagens

## Exemplo de uma aplicação em Python

### Exemplo de um problema de classificação usando fuzzy clustering

```Python

```
