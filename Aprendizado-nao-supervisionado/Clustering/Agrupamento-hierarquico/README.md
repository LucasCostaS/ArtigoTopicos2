# Agrupamento hierárquico

## O que é o metodo de Agrupamento hierárquico?

O agrupamento hierárquico ( tambem chamado de Hierarchical clustering) é uma tecnica de clusterização que em contruir uma hierarquia de agrupamentos que tenha uma ordenação estabelecida, como por exemplo uma hierarquia de cima para baixo ( Top-Down ) ou de baixo para cima ( Bottom-up ). O K-Menas n se enquadra nessa categoria pois nao gera agrupamentos em uma hierarquia.

## A matemática por trás

Nesse metodo é necessario seguir uma sequencia de passos como por exemplo indentificar os dois agrupamentos mais proximos , mescla-los e repetir o processo ate se obter o resultado desejado. Para poder-mos fazer isso de forma a atingir nosso objetivo são usados dois criterios:

### Métrica de distancia

É o calculo envolvendo a distancia entre os pontos podendo ser

- Distância euclidiana:
<div>
<img src="https://miro.medium.com/max/964/1*mk8ZyVvsyIf7zvGrW9WT6g.png" width="300">
</div>

- Distância euclidiana quadrada
<div>
<img src="https://miro.medium.com/max/816/1*ktEGPP1JttvzdwvXuMbE8w.png" width="300">
</div>

- Distância manhattan
<div>
<img src="https://miro.medium.com/max/816/1*ktEGPP1JttvzdwvXuMbE8w.png" width="300">
</div>

- Distância máxima
<div>
<img src="https://miro.medium.com/max/796/1*0K2Qf6pJO4wBp8h5UdFU-Q.png" width="300">
</div>

### Criterio de ligação

## Vantagens e Desvantagens

### Vantagens

Os métodos hierárquicos da Análise de Cluster carregam a característica de um algoritmo que é capaz de prover mais de um tipo de partição dos dados. Automaticamente vários agrupamentos possíveis são gerados, onde um Cluster pode se misturar a outro em determinado passo do algoritmo.

### Desvantagens

## Exemplo de uma aplicação em Python

### Exemplo de um problema de classificação usando Agrupamento hierárquico

```Python

```
