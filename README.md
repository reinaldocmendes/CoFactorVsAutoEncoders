# CoFactorVsAutoEncoders
Jupiter Notebook com Resultados do algoritmo CoFactor

# Definição dos Dados - Descritivo
Os valores apresentados nos gráficos, correspondem aos resultados obtidos do Algoritmo CoFactor. A Barra amarela correponde a entrada padrão dos dados, no qual o algoritmo trabalha com a co-ocorrência de itens. As demais barras correpondem a entrada gerada atráves do procedimento a descrito abaixo.

# Redes Neurais Convolutivas
O dataset de imagens (ml20m) foi aplicado a quatro redes neurais convolutivas para extração de suas features. Foram elas Resnet50, Vgg16, Vgg19 e Xception. Uma vez que essas features foram extraídas, uma segunda feature foi extraída de informações textuais do mesmo dataset utilizando uma rede neural chamada Doc2vec.

Cada feature extraídas da imagens foram concatenadas com a feature de informações textuais, gerando um novo vetor de features.

Resnet50+Doc2Vec / Vgg16+Doc2Vec / Vgg19+Doc2Vec / Xception+Doc2Vec

# AutoEnconder's
Cada vetor de features "concatenado" foi aplicado a um tipo de AutoEnconder com o objetivo de gerar uma nova representação do vetor de features original. Os autoencoder's utilizados foram Sparse AutoEncoder, Convolutional AutoEnconder (CAE) e Varitional AutoEncoder (VAE).

As representações geradas do vetor de featuares concatenado, após aplicadas nos autoencoder's foram:

10% - Uma representação com 10% do tamanho do vetor original

20% - Uma representação com 20% do tamanho do vetor original

30% - Uma representação com 30% do tamanho do vetor original

40% - Uma representação com 40% do tamanho do vetor original

50% - Uma representação com 50% do tamanho do vetor original

60% - Uma representação com 60% do tamanho do vetor original

70% - Uma representação com 70% do tamanho do vetor original

80% - Uma representação com 80% do tamanho do vetor original

90% - Uma representação com 90% do tamanho do vetor original

100% - Uma representação com 100% do tamanho do vetor original

# Metricas de Avaliação
Medidas de avaliação (ranked-based) foram utilizadas para medir o desempenho da recomendação do algoritmo ao mudar seu dataset de entrada em comparação com o dataset original proposto (co-ocorrência).

Para cada usuário, todas as métricas comparam a classficação prevista de itens "não observados" com sua classificação real. As medidas utilizadas foram Recall, NDCG e Map.

Nos resultados apresentados nos gráficos que seguem, foram considerados nos experimentos um "ranked list" de tamanhos fixados em: 10, 20, 50 e 100, para cada medida de avaliação, por exemplo, NDCG@20 significado que foi considerado um ranked list dos 20 itens no topo da lista.

# Análise Geral
Nós Gráficos é possível verificar que mesmo alterando o tipo da rede neural eles apresentavam o mesmo comportamento com resultados muito similares e por vezes iguais.

Em todas as Comparações o BaseLine (CoFactor) utilizado apresentou melhor resultado do que as represntações propostas do vetor original.

A razão dos resultados serem muitos similares ou iguais, mesmo modificando a representação do vetor original ainda é desconhecida.

# Organização dos Arquivos
Foram criados 3 arquivos notebook, no qual, cada um deles contém um conjunto de gráficos comparando os resultados do BaseLine com as represetaçoes dos AutoEncoder's (sparse, vae, cae) aplicados sobre cada vetor gerado pelas redes neuras (ResNet50, Vgg16, Vgg19 e Xception).
