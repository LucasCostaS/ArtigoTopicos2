# Agrupamento K-means

## O que é o metodo de Agrupamento K-means?

É um metodo de clustering que consiste em aproximar elementos ou pontos de dados em agrupamentos. Neste metodo é definido um numero K que representa a quantidade de agrupamentos que devem ser criados ao final do processo, cada agrupamento representa caracteristicas unicas daqueles individuos de modo que um dado nao pode pertencer a mais de um agrupamento.

## A matemática por trás

Este metodo consite em definir centroides ( ponto medio ) para os K agrupamentos e definir a qual agrupamento o dado esta mais proximo ( tem maior similaridade )

- Calculo para definir e recalcular o centroide de cada cluster ( agrupamento )
<div>
<img src="https://muthu.co/wp-content/uploads/2018/07/Snip20180707_101.png" width="300">
</div>

- Calculo para definir a distancia entre um ponto ate o centroide de cada agrupamento
<div>
<img src="https://muthu.co/wp-content/uploads/2018/07/Snip20180707_99.png" width="300">
</div>

## Vantagens e Desvantagens

### Vantagens

- Facil implementação

- Quando ha grande quantidades de variaveis desempenha melhor que outros metodos de agrupamento.

- Produz cluters mais precisos e compactos que metodos como o hierarquico

### Desvantagens

- Dificuldade em definir um valor K ideal para o modelo

- as sementes iniciais tem um grande peso no resultado final do processo

## Exemplo de uma aplicação em Python

### Exemplo de um problema de classificação usando Agrupamento K-means

```Python

```
