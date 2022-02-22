# O agrupamento difuso

## O que é o metodo fuzzy clustering (agrupamento difuso)?

    Agrupar dados é uma tarefa muito importante em mineração de dados, processamento de imagens e em problemas de reconhecimento de padrões. Um dos algoritmos de agrupamentos mais popular é o Fuzzy C-Means (FCM). Esta tese propõe aplicar uma nova forma de calcular os centros dos clusters no algoritmo FCM, que denominamos de ckMeans, e que pode ser também aplicada em algumas variantes do FCM, em particular aqui aplicamos naquelas variantes que usam outras distâncias. Com essa modificação, pretende-se reduzir o número de iterações e o tempo de processamento desses algoritmos sem afetar a qualidade da partição ou até melhorar o número de classificações corretas em alguns casos. Também, desenvolveu-se um algoritmo baseado no ckMeans para manipular dados intervalares considerando graus de pertinência intervalares. Este algoritmo possibilita a representação dos dados sem conversão dos dados intervalares para pontuais, como ocorre com outras extensões do FCM que lidam com dados intervalares. Para validar com as metodologias propostas, comparou-se o agrupamento ckMeans com os algoritmos K-Means (pois o algoritmo proposto neste trabalho para cálculo dos centros se assemelha à do K-Means) e FCM, considerando três distâncias diferentes. Foram utilizadas várias bases de dados conhecidas. No caso, os resultados do ckMeans intervalar, foram comparadas com outros algoritmos de agrupamento intervalar quando aplicadas a uma base de dados intervalar com a temperatura mínima e máxima do mês de um determinado ano, referente a 37 cidades distribuídas entre os continentes

## Uso

## A matemática por trás

## Vantagens e Desvantagens

### Vantagens

### Desvantagens

## Exemplo de uma aplicação em Python

### Exemplo de um problema de classificação usando fuzzy clustering

```Python

```
