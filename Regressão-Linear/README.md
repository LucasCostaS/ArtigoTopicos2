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

## A matemática por trás

Para ser aplicado é necessário que haja uma boa correlação linear (positiva ou negativa) entre os dados, ou seja, quando o relacionamento ou associação entre os dados pode ser definido com uma reta.

Mas o que é correlação?

Em probabilidade e estatística, correlação, dependência ou associação é qualquer relação estatística (causal ou não causal) entre duas variáveis e correlação é qualquer relação dentro de uma ampla classe de relações estatísticas que envolva dependência entre duas variáveis. Por exemplo, a correlação entre a estatura dos pais e a estatura dos pais e dos filhos. Na regressão Linear usamos a Correlação Linear de Pearson.

Correlação Linear de Pearson: mede a correlação linear entre a nuvem de pontos. O resultado varia entre -1 e 1:
-1: Correlação linear perfeita negativa
1: Correlação linear perfeita positiva
0: Não tem correlação linear

<div>
<img src="https://miro.medium.com/max/1400/1*7hpPonf1E0rUJ6xETLySKQ.png" width="600">
</div>

O objetivo da regressão linear é encontrar uma reta que consiga definir bem os dados e minimizar a diferença entre o valor real e a saída calculada pelo modelo. A função que representa bem a regressão linear é dado a seguir:

<div>
<img src="https://miro.medium.com/max/1400/0*E-6Yud1vgsM6pV6u" width="600">
</div>

Onde ***w<sub>0</sub>*** (representa o ponto inicial da reta)e ***w<sub>1</sub>*** (representa a inclinação da reta, ou seja, o quanto que essa variável cresce conforme o tempo passa) são variáveis que o algoritmo calcula para poder definir a reta, e ***x<sub>1</sub>*** seria o atributo de entrada que foi dada ao modelo. E com esses valores ele consegue fazer as previsões.

Por exemplo, vamos supor que o algoritmo calculou o valor de ***w<sub>0</sub>*** e ***w<sub>1</sub>*** e definiu que seria respectivamente 0 e 10. O valor de ***x<sub>1</sub>*** será 5.1, portanto o cálculo realizado será:
Yˆ= f(x) = 0 + 10 * 5.1
Yˆ= 51

Se você fizer o valor real menos o valor previsto, poderá obter o erro/ resíduo. Portanto a equação ficaria:
residuo = Y - Yˆ

O resíduo representa a quantidade da variabilidade que Y que o modelo ajustado não consegue explicar. Os resíduos contém informação sobre o motivo do modelo não ter se ajustado bem aos dados.

***Métricas de validação***

SQR (Soma dos Quadrados dos Resíduos)

Soma dos quadrados dos resíduos, mostra a variação de Y que não é explicada pelo modelo elaborado. É a medida da variação que não pode ser explicada.

<div>
<img src="https://miro.medium.com/max/1400/1*YC_sAM5AZFmkNeol4BdynA.png" width="600">
</div>


R²

O R² é uma medida estatística de quão próximos os dados estão da linha de regressão ajustada. Ele também é conhecido como o coeficiente de determinação ou o coeficiente de determinação múltipla para a regressão múltipla.

O R² está sempre entre 0 e 1:

0: indica que o modelo não explica nada da variabilidade dos dados de resposta ao redor de sua média.

1: indica que o modelo explica toda a variabilidade dos dados de resposta ao redor de sua média.


MAE (Erro Médio absoluto)

O erro médio absoluto (MAE) é a métrica de erro de regressão mais simples de entender. Ele calcula o valor dos resíduos para cada um dos pontos e depois é tirado a média de todos esses resíduos.


<div>
<img src="https://miro.medium.com/max/1400/0*nruMtzDtZjauyUQ7.jpg" width="600">
</div>


MSE (Média dos erros ao quadrado)

O MSE é apenas o cálculo do erro mas elevamos ao quadrado.

<div>
<img src="https://miro.medium.com/max/1400/1*EI9mQhCNLrdgTXVAp-6tXg.png" width="600">
</div>

Por estarmos elevando o resíduo ao quadrado, não podemos comparar ele com o valor de MAE, pois ele sempre será maior portanto faz mais sentido comparar o MSE com o valor do MSE de outro modelo.

## Vantagens e Desvantagens

#Vantagens

A análise de regressão ajuda gerentes e donos de empresas a prever condições futuras, dar suporte quantitativo ao julgamento dos gerentes, apontar falhas no pensamento gerencial e fornecer novos insights que podem ajudar os tomadores de decisão a mudar seus negócios para um futuro mais lucrativo.

**Prever o futuro**

Uma das principais vantagens das técnicas de previsão baseadas em regressão é que elas usam pesquisa e análise para prever o que provavelmente acontecerá no próximo trimestre, ano ou até mais longe no futuro, de acordo com AH Studenmund, autor de “Using Econometrics”. Para os proprietários de pequenas empresas, a previsão baseada em regressão pode fornecer informações sobre como impostos mais altos, mudanças nos gastos do consumidor ou mudanças na economia local, por exemplo, afetarão suas empresas.

**Decisões de apoio**

As técnicas de regressão e previsão podem dar um ângulo científico ao gerenciamento de pequenas empresas, reduzindo grandes quantidades de dados brutos a informações acionáveis. Em alguns casos, a análise apoiará o sentimento do gerente.

Por exemplo, um gerente que acredita na expansão para uma nova instalação aumentará o tráfego de clientes e as vendas poderão encontrar suporte em um modelo de regressão que encontre uma correlação entre o tamanho da instalação e as receitas da empresa.

**Corrigindo erros**

Embora a previsão e a regressão possam dar suporte empírico à intuição gerencial, essas técnicas também podem corrigir o pensamento gerencial quando as evidências indicam o contrário. Assim como a regressão pode fornecer suporte quantitativo para as decisões, ela também pode mostrar onde a intuição de uma pequena empresa está equivocada.

Por exemplo, um gerente de loja de varejo pode acreditar que o aumento do número de horas de compras aumentará muito as vendas. Uma análise de regressão, no entanto, pode demonstrar que as horas mais longas não aumentam significativamente as vendas o suficiente para justificar o aumento dos custos operacionais, como o trabalho adicional dos funcionários.

**Novas ideias**

Grandes conjuntos de dados têm o potencial de gerar novas informações valiosas sobre empresas e suas operações. No entanto, os dados não falam por si, tornando a análise necessária. As técnicas de regressão e previsão podem gerar novos insights para os gerentes, revelando padrões e relacionamentos que eles não haviam percebido ou considerado anteriormente.

Por exemplo, a análise de dados de vendas e compras pode revelar padrões de compra específicos em determinados dias da semana ou em determinadas épocas do ano. Esses insights podem sinalizar a necessidade de garantir que esses produtos estejam em oferta suficiente para esses períodos de alta demanda.

# Desvantagens

**Regressão linear é limitada a relacionamentos lineares**

Por sua natureza, a regressão linear analisa apenas relações lineares entre variáveis dependentes e independentes. Isto é, pressupõe que existe uma relação direta entre eles. Às vezes isso está incorreto. Por exemplo, a relação entre renda e idade é curva, ou seja, a renda tende a aumentar nas primeiras partes da vida adulta, se achatando na idade adulta e declinando depois que as pessoas se aposentam. Você pode dizer se isso é um problema, olhando representações gráficas dos relacionamentos.

**Regressão Linear olha apenas para a média da variável dependente**

A regressão linear analisa uma relação entre a média da variável dependente e as variáveis independentes. Por exemplo, se você observar a relação entre o peso ao nascer dos bebês e as características maternas, como a idade, a regressão linear examinará o peso médio dos bebês nascidos de mães de diferentes idades.

No entanto, às vezes você precisa olhar para os extremos da variável dependente, por exemplo, bebês correm risco quando seus pesos estão baixos, então você gostaria de ver os extremos neste exemplo.

Assim como a média não é uma descrição completa de uma única variável, a regressão linear não é uma descrição completa das relações entre as variáveis. Você pode lidar com esse problema usando a regressão quantílica.

**Os dados devem ser independentes**

A regressão linear assume que os dados são independentes. Isso significa que as pontuações de um sujeito (como uma pessoa) não têm nada a ver com as de outro. Isso é muitas vezes, mas nem sempre, sensato. Dois casos comuns em que não faz sentido são agrupados no espaço e no tempo.

Um exemplo clássico de agrupamento no espaço são os resultados dos testes dos alunos, quando você tem alunos de várias classes, séries, escolas e distritos escolares. Alunos da mesma turma tendem a ser parecidos em muitos aspectos, ou seja, muitas vezes vêm dos mesmos bairros, possuem os mesmos professores, etc. Assim, não são independentes.

Exemplos de clustering no tempo são quaisquer estudos em que você mede os mesmos assuntos várias vezes. Por exemplo, em um estudo de dieta e peso, você pode medir cada pessoa várias vezes. Esses dados não são independentes porque o que uma pessoa pesa em uma ocasião está relacionado ao que ela pesa em outras ocasiões. Uma maneira de lidar com isso é com modelos multiníveis.

