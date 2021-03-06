# Decomposição de Valor Singular

## O que é o metodo Decomposição de Valor Singular?

Em álgebra linear, a decomposição em valores singulares ou singular value decomposition (SVD) é a fatoração de uma matriz real ou complexa, com diversas aplicações importantes em processamento de sinais e estatística.

Esta técnica estatística multivariada ajuda a resolver problemas complexos nas ciências atmosféricas. A análise empírica da função ortogonal e a análise dos componentes principais são conjuntos de procedimentos semelhantes para a mesma técnica introduzida em 1956 por Edward Lorenz.

A decomposição de valores singulares ajuda a reduzir conjuntos de dados contendo um grande número de valores. Além disso, este método também é útil para gerar soluções significativas para menos valores. No entanto, estes menos valores compreendem também uma imensa variabilidade disponível nos dados originais.

Os dados revelam grandes correlações espaciais nas ciências geofísicas e atmosféricas. Uma análise de Decomposição de Valores Singulares apoia e produz resultados para uma demonstração mais compacta destas correlações. Ao utilizar conjuntos de dados multivariados, é possível produzir conhecimentos sobre variações temporais e espaciais. Estas variações exibem dados após a análise.

## Uso

O algoritmo de Kabsch (Kabsch algorithm), também conhecido como Wahba's problem, utiliza a SVD para calcular a rotação ótima (no sentido dos mínimos quadrados) que alinha um conjunto de pontos com um conjunto de pontos correspondentes. Isso tem aplicações para a comparação de estruturas moleculares e em problemas relacionados a modelos 3D em visão computacional e robótica.

A classificação autônoma de números escritos à mão é um problema clássico na computação de reconhecimento de padrões. E existem diversos métodos de abordagem para esse problema e seus derivados. No entanto, para atingir grandes performances, muitas dessas abordagens são eventualmente muito complexas ou exigem um poder de processamento muito grande.
Com uso de decomposição de valor singular (SVD) para determinar as principais características a serem consideradas na classificação é possível reduzir significativamente o número de informação necessária para o reconhecimento.

## A matemática por trás

Suponha-se que M é uma matriz m _ n cujas entradas vêm de um corpo de escalares K, que pode ser tanto o corpo de números reais ou o corpo de números complexos. Então existe uma fatorização da forma: M=UΣV_, onde U é uma matriz unitária m \* m sobre K, a matriz Σ é uma matriz diagonal m \* n com números reais não-negativos na diagonal, e V\*, uma matriz unitária n×n sobre K, denota a transposta conjugada de V. Tal fatorização é chamada de decomposição em valores singulares de M.

Considere-se a matriz 4×5

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/0d5d3df9cf619062481ab2a6b328467990152f1a" width="250">
</div>

A decomposição em valores singulares desta matriz é dada por UΣV\*

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/73fdf5fe339a08566cccb833c860558092532f74" width="700">
</div>

Note-se que Σ contém apenas zeros fora da diagonal. Ademais, como as matrizes U e V\* são unitárias, multiplicando-se por suas respectivas conjugadas transpostas gera matrizes identidades, como mostrado a seguir. Nesse caso, como U e V\* são reais, cada uma delas é uma matriz ortogonal.

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/a7f128976e087ec8136d54eeaab90a2eda2a09bc" width="700">
</div>
<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/43daa2de3e7835aba9c75c1eef02bbe5c2d6f687" width="700">
</div>

Deve-se notar que esta decomposição em valores singulares em particular não é única. Escolhendo-se V tal que

<div>
<img src="https://wikimedia.org/api/rest_v1/media/math/render/svg/ff594573fad8316d17c3bf71b297e6135d7d3d64" width="350">
</div>
é também uma decomposição válida em valores singulares.

## Vantagens e Desvantagens

### Vantagens

- Simplifica os dados
- Remove o ruído
- Pode melhorar os resultados do algoritmo.

### Desvantagens

- Os dados transformados podem ser difíceis de entender.

## Exemplo de uma aplicação em Python

### Exemplo de um problema de classificação usando Decomposição de valor singular

Exemplo com base em um problema apresentado na documentação do sckit learn

```Python
from sklearn.decomposition import TruncatedSVD
from scipy.sparse import csr_matrix
import numpy as np
np.random.seed(0)
X_dense = np.random.rand(100, 100)
X_dense[:, 2 * np.arange(50)] = 0
X = csr_matrix(X_dense)
svd = TruncatedSVD(n_components=5, n_iter=7, random_state=42)
svd.fit(X)
TruncatedSVD(n_components=5, n_iter=7, random_state=42)
print(svd.explained_variance_ratio_)
[0.0157... 0.0512... 0.0499... 0.0479... 0.0453...]
print(svd.explained_variance_ratio_.sum())
0.2102...
print(svd.singular_values_)
[35.2410...  4.5981...   4.5420...  4.4486...  4.3288...]

```
