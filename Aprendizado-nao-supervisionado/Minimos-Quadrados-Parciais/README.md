# Mínimos quadrados parciais

## O que é o metodo Mínimos quadrados parciais?
Como o nome indica, os Mínimos Quadrados Parciais estão relacionados aos Mínimos Quadrados Ordinários: a abordagem matemática padrão para ajustar uma Regressão Linear.

A regressão por mínimos quadrados parcial (regressão PLS) é um método estatístico que tem alguma relação com a regressão de componentes principais; em vez de encontrar hiperplanos de variância máxima entre a resposta e as variáveis independentes, encontra um modelo de regressão linear projetando as variáveis preditas e as variáveis observáveis para um novo espaço.

<div>
<img src="https://cdn.xlstat.com/media/feature/0001/01/thumb_367_feature_medium.png" width="600">
</div>

O mínimo quadrado parcial foi introduzido pelo estatístico sueco Herman O. A. Wold, que então o desenvolveu com seu filho, Svante Wold. Um termo alternativo para PLS (e mais correto de acordo com Svante Wold) é projeção para estruturas latentes, mas o termo mínimos quadrados parciais ainda é dominante em muitas áreas.

Alguns programas diferenciam PLS 1 de PLS 2. PLS 1 corresponde ao caso em que existe apenas uma variável dependente. O PLS 2 corresponde ao caso em que existem várias variáveis dependentes.

## Uso

A regressão PLS é usada principalmente nas indústrias química, farmacêutica, alimentícia e plástica. Uma aplicação comum é modelar a relação entre medidas espectrais (NIR, IR, UV), que incluem muitas variáveis que são frequentemente correlacionadas entre si, e composição química ou outras propriedades físico-químicas. Na regressão PLS, a ênfase está no desenvolvimento de modelos preditivos. Portanto, geralmente não é usado para filtrar variáveis que não são úteis para explicar a resposta.

A correlação PLS (PLSC) é outra metodologia relacionada à regressão PLS, que tem sido usada em neuroimagem e mais recentemente na ciência do esporte, para quantificar a força da relação entre os dados conjuntos. Normalmente, o PLSC divide os dados em dois blocos (subgrupos) cada um contendo uma ou mais variáveis e, em seguida, usa a decomposição de valor singular (SVD) para estabelecer a força de qualquer relacionamento (ou seja, a quantidade de informações compartilhadas) que possa existir entre os dados. dois subgrupos de componentes. Ele faz isso usando SVD para determinar a inércia (ou seja, a soma dos valores singulares) da matriz de covariância dos subgrupos em consideração.

## A matemática por trás
O modelo subjacente geral de PLS multivariado é
<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/f99c8237329d8854cd91037f9d609e151dde4f51" width="200">
</div>
onde X é uma matriz n * m de preditores, Y é uma matriz n * p de respostas; T e U são matrizes n * l que são, respectivamente, projeções de X (a pontuação X, componente ou matriz fatorial) e projeções de Y (a pontuação Y); P e Q são, respectivamente,  m * l e p * l matrizes de carregamento ortogonal; e as matrizes E e F são os termos de erro, assumidos como variáveis normais aleatórias independentes e identicamente distribuídas. As decomposições de X e Y são feitas de forma a maximizar a covariância entre T e U.


## Vantagens e Desvantagens

### Vantagens
Em alguns domínios, pode acontecer que você tenha muitas variáveis independentes em seu modelo, muitas das quais estão correlacionadas com outras variáveis independentes. PLS é uma solução para este caso: permite reduzir a dimensionalidade de variáveis correlacionadas e modelar as informações subjacentes, compartilhadas, dessas variáveis (em variáveis dependentes e independentes).

Uma segunda grande vantagem de PLSs é que é um método que pode modelar múltiplas variáveis de resultado. Muitas estatísticas e modelos de Machine Learning não podem lidar diretamente com várias variáveis de resultado.
Muitas vezes podem ser encontradas soluções para esses modelos. Por exemplo, construir um modelo por variável. No entanto, especialmente para casos de uso analíticos, pode ser essencial manter tudo em um modelo, pois a interpretação de um modelo multivariado será diferente da interpretação de muitos modelos univariados.

### Desvantagens
As principais limitações são um risco maior de ignorar as correlações "reais" e a sensibilidade à escala relativa das variáveis do descritor.

Algumas implementações do PLS parecem ter propriedades perigosas (principalmente uma com uma taxa de 100% de falsos positivos) e o PLS geralmente parece inflar o erro Tipo I para pequenos efeitos. A última propriedade pode dar a impressão de atenuar o erro de medição (mas apenas fornece um viés que às vezes pode neutralizar a atenuação decorrente do erro de medição).

## Exemplo de uma aplicação em Python

### Exemplo de um problema de classificação usando Mínimos quadrados parciais

```Python

```
