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

O algoritmo FCM tenta particionar uma coleção finita de N elementos X = {x1 , ... xn} em uma coleção de c clusters difusos, respeitando algum critério determinado.

Dado um conjunto finito de dados, o algoritimo retorna uma lista de c centros de cluster C = {C1 , ... , Cc}e uma matriz de partição, onde cada elemento diz o grau que o elemento xi pertence ao cluster Cj.

O FCM visa minimizar uma função objetiva:

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/3116dcd0197dc45eea812c23e79314eb4edac8ab" width="300">
</div>

onde

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/0072b0e3d088f0189660ff5cc29335399b28b0b7" width="300">
</div>

## Vantagens e Desvantagens

### Vantagens

- Busca o melhor resultado para conjunto de dados sobrepostos e desempenha comparativamente melhor que o K-Means

- Diferentemente do metodo K-Means, o ponto dos dados é associado a cada centro de cada agrupamento, como resultado o ponto pode pertencer a mais de um centro de cluster

### Desvantagens

- Definir um valor para C que limita a quantidade de clusters

- O calculo de distancia euclidiana pode ponderar de forma desigual os fatores subjacentes

## Exemplo de uma aplicação em Python

### Exemplo de um problema de classificação usando fuzzy clustering

```Python

```
