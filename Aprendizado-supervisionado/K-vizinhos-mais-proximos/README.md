# K-Vizinhos mais proximos

## O que é K-Vizinhos mais proximos?

O KNN (K Nearest Neighbor) é um algoritmo não pramétrico, aonde a estrutura do modelo será determinada pelo dataset utilizado. Este algoritmo também é conhecido como de aprendizado lento ou melhor dizendo, é um algoritmo preguiçoso, o termo certo é “lazy”. Os algoritmos do tipo lazy, não necessitam de dados de treinamento para se gerar o modelo, o que diminui em partes o processo inicial, mas em contrapartida gerará uma necessidade de analise posterior mais apurada. No caso de algoritmos que não necessitam de treinamento, todos os dados obtidos no dataset serão utilizados na fase de teste, resultando em um treinamento muito rápido e em um teste e validação lentos, momento o qual necessitamos estar bem atentos aos resultados gerados.

O funcionamento do KNN é bem simples, imagine que você tem dados de:

- imagens de bolinhas roxas
- imagens de bolinhas amarelas
- Uma imagem de uma bolinha que você não sabe se é roxa ou amarela, mas tem todos os dados sobre ela.

<div>
<img src="https://miro.medium.com/max/1400/0*GWBuXGRP3WpB2cu3" width="600">
</div>

Cada linha se refere a uma imagem e cada coluna se refere a um pixel dessa imagem, na última coluna nós temos a classe (cor) de cada uma das bolinhas, R ->roxo, e A -> amarelo, temos lá 5 imagens (5 linhas) de bolinhas, cada uma com sua classificação, você pode tentar descobrir a cor (no caso a classe) da nova imagem (uma imagem de uma bolinha que você não sabe a cor) de N maneiras, uma dessas N maneiras é ficar comparando essa nova imagem com todas as outras, e ver com qual ela se parece mais, se os dados dessa nova imagem (que você não sabe a classe dela) são mais próximos dos dados das imagens de bolinhas amarelas, então a cor da imagem nova que não está classificado é amarela, se os dados da imagem nova, forem mais parecidos com os dados das imagens de bolinha roxa, então essa a cor da bolinha da imagem nova é roxa.
No caso do KNN, ele não “compara” o seu novo dado (não classificado) com todos os outros de fato, na verdade ele executa um cálculo matemático para medir a distância entre os dados para fazer sua classificação. Esse cálculo que estou falando pode ser qualquer um que meça a distância entre dois pontos, como por exemplo: Euclidiana, Manhattan, Minkowski, Ponderada e etc.

## Usos

O algoritmo KNN pode competir com os modelos mais precisos porque faz previsões altamente precisas. Portanto, você pode usar o algoritmo KNN para aplicativos que exigem alta precisão, mas que não exigem um modelo legível por humanos.

A qualidade das previsões depende da medida de distância. Portanto, o algoritmo KNN é adequado para aplicações para as quais há conhecimento de domínio suficiente. Este conhecimento suporta a seleção de uma medida apropriada.

KNN pode ser usado para Sistemas de Recomendação. Embora no mundo real, algoritmos mais sofisticados sejam usados ​​para o sistema de recomendação. O KNN não é adequado para dados de alta dimensão, mas o KNN é uma excelente abordagem de linha de base para os sistemas. Muitas empresas fazem uma recomendação personalizada para seus consumidores, como Netflix, Amazon, YouTube e muito mais.

Pode pesquisar documentos semanticamente semelhantes. Cada documento é considerado como um vetor. Se os documentos estiverem próximos uns dos outros, isso significa que os documentos contêm tópicos idênticos.

O KNN pode ser efetivamente usado na detecção de valores discrepantes. Um exemplo é a detecção de fraude de cartão de crédito.

## A matemática por trás

As etapas de um algoritmo KNN são:
1. Recebe um dado não classificado.
2. Mede a distância (Euclidiana, Manhattan, Minkowski ou Ponderada) do novo; dado com todos os outros dados que já estão classificados.
3. Obtém as X(no caso essa variável X é o parâmetro K) menores distâncias.
4. Verifica a classe de cada da um dos dados que tiveram a menor distância e conta a quantidade de cada classe que aparece.
5. Toma como resultado a classe que mais apareceu dentre os dados que tiveram as menores distâncias.
6. Classifica o novo dado com a classe tomada como resultado da classificação.

Para calcular a distância entre dois pontos (sua nova amostra e todos os outros dados que você tem no seu dataset) é muito simples, como dito anteriormente, há várias formas de obter esse valor, neste artigo vamos usar a distância euclidiana, pois é uma das mais usadas.

<div>
<img src="https://miro.medium.com/max/696/0*zUorr2mw9xMFpoQp" width="500">
</div>

É com essa fórmula que você vai verificar a distância entre 1 ponto(sua amostra nao classificada) e 1 outro ponto do seu dataset(1 outro dado já classificado) para então ver a similaridade dos dois, quanto menor é o resultado dessa conta mais é a similaridade entre esses dois dados. Esse cálculo será rodado varias vezes, até ter rodado em todos os dados, no final, você vai ter um array(vamos usar um array como exemplo) com o resultado de cada vez que você calculou a distância(no caso, a similaridade) do seu dado não classificado para um outro dado já classificado.

O calculo de fato, é simples mas leia com calma essa parte, basicamente você vai tirar a raiz quadrada da soma dos resultados da subtração de cada característica do ponto1 (amostra não classificada) para o ponto2 (amostra já classificada).

Depois que obtiver a distância Euclidiana do ponto 1 para todos os outros pontos, aí você vai ordená-las do menor pro maior, verificar quais são as K(3 por exemplo) menores distâncias e verificar qual é a classe que aparece mais, a classe que mais aparecer vai ser a classe que você vai usar para classificar o ponto 1 (que desde o início não estava classificada).

## Vantagens e Desvantagens

### Vantagens

- O algoritmo é simples e fácil de implementar.
- Não há necessidade de construir um modelo, ajustar vários parâmetros ou fazer suposições adicionais.
- O algoritmo é versátil. Ele pode ser usado para classificação, regressão e pesquisa.


### Desvantagens

- O algoritmo fica significativamente mais lento à medida que o número de exemplos e/ou preditores/variáveis ​​independentes aumenta.
