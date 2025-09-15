
 Sistema de Recomendação por Imagens

Este projeto implementa um sistema de recomendação baseado em similaridade visual.
Em vez de usar atributos textuais (preço, marca, descrição), o modelo encontra itens visualmente parecidos com a imagem consultada pelo usuário.

 Objetivo

Treinar uma rede de Deep Learning pré-treinada (MobileNetV2) para extrair features (embeddings) das imagens.

Criar um índice de similaridade entre os vetores de embeddings.

Dada uma imagem de consulta, retornar as imagens mais similares visualmente.

 Dataset

Utilizado o Fashion-MNIST, disponível no tensorflow.keras.datasets.

Contém 70.000 imagens de roupas, em 10 classes (camisetas, sapatos, bolsas etc).

Para evitar consumo excessivo de memória no Google Colab, foi usado um subset:

10.000 imagens de treino

2.000 imagens de teste

 Tecnologias Utilizadas

Python 3.10+

TensorFlow / Keras – extração de embeddings (MobileNetV2 pré-treinada no ImageNet).

scikit-learn (NearestNeighbors) – busca de itens mais similares.

Matplotlib – visualização dos resultados.

Google Colab – execução do projeto sem necessidade de instalação local.


 Pipeline do Projeto

Carregar dataset Fashion-MNIST

Pré-processar imagens

Normalização

Conversão para RGB (3 canais)

Redimensionamento para 224x224

Extrair embeddings usando MobileNetV2 (camada pooling="avg").

Criar índice de vizinhos mais próximos (NearestNeighbors com métrica de cosseno).

Consultar recomendações:

Entrada: uma imagem do dataset de teste.

Saída: 5 imagens mais parecidas do dataset de treino.


Exemplo de uso:

# Exibir recomendações para a 10ª imagem de teste
recomendar(10)

 Exemplo de Saída

Imagem consultada: uma camiseta.

Recomendações: 5 camisetas visualmente parecidas do dataset de treino.
