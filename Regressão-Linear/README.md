# Regressão Linear

## O que é regressão linear?

Sua origem vem da correlação linear, que é a verificação da existência de um relacionamento entre duas variáveis. Ou seja, dado X e Y, quanto que X explica Y. Para isso, a regressão linear utiliza os pontos de dados para encontrar a melhor linha de ajuste para modelar essa relação.

O resultado da regressão linear é sempre um número. É utilizada adequadamente quando o dataset apresenta algum tipo de tendência de crescimento/descrescimento constante.


Antes de prosseguir, há alguns conceitos importantes que precisam estar bem claros em mente.

Variável independente ou preditora: é aquela que será passada para o modelo, tendo influência na variável que queremos encontrar. Por exemplo: Se queremos prever as vendas de sorvete, a estação do ano pode interferir nas vendas.

Variável alvo ou dependente: é a variável que queremos prever. No exemplo acima seria as vendas de sorvete.


Existem 2 tipos de regressão linear: simples e a múltipla.

Regressão linear simples : refere-se quando temos somente uma variável independente ***x*** para fazermos a predição.

Regressão linear múltipla: refere-se a várias variáveis independentes ***x*** usadas para fazer a predição.

<div>
<img src="https://images.squarespace-cdn.com/content/v1/5a2a067e8dd04151f6e8250d/1592816786422-TU0MNDRCXD7Y4JAT3LGP/regressao+linear2.jpg" width="600">
</div>

<div>
<img src="http://www.sakurai.dev.br/images/posts/2021-01-04-regressao-linear-multipla-04.png" width="600">
</div>

## Usos

A análise de regressão pode ser utilizada para resolver os seguintes tipos de problemas:

Determinar quais variáveis explanatórias estão relacionadas à variável dependente.

Entender o relacionamento entre as variáveis dependentes e explanatórias.

Prever valores desconhecidos da variável dependente.

***Exemplos***

Um analista de uma pequena cadeia de varejo está estudando o desempenho de diferentes lojas. O analista deseja saber o motivo de algumas lojas estarem tendo um volume de vendas inesperadamente baixo. O analista cria um modelo de regressão com variáveis explanatórias como idade mediana e renda na vizinhança, como também, a distância até centros de varejo e o transporte público, para determinar quais variáveis estão influenciando as vendas.

Um analista de um departamento de educação está estudando os efeitos dos programas de café da manhã na escola. O analista cria um modelo de regressão dos resultados de escolaridade, como a taxa de graduação, utilizando variáveis explanatórias como tamanho da turma, renda familiar, orçamento escolar per capita e proporção de alunos tomando café da manhã diariamente. A equação do modelo pode ser utilizada para determinar o efeito relativo de cada variável nos resultados de escolaridade.

O analista de uma organização não governamental está estudando as emissões globais de gases de efeito estufa. O analista cria um modelo de regressão para as emissões mais recentes para cada país utilizando variáveis explanatórias como produto interno bruto (PIB), população, produção de eletricidade utilizando combustíveis fósseis e uso de veículos. O modelo pode então ser utilizado para prever futuras emissões de gases de efeito estufa utilizando o PIB previsto e os valores da população.

