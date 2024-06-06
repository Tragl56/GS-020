Integrantes da equipe: 
 
Enrico do Nascimento Ferreira Galdino - rm552082 – 2TDSPH 
Eduardo Ferreira Silva de Jesus - rm98410 – 2TDSPN 
Leonardo Matheus Mariano Guedes da Silva - rm99824 – 2TDSPN 
Luiz Felipe dos Santos Tragl - rm99476 – 2TDSPB 
Pedro Henrique Chersoni Lins - rm99866 - 2TDSPW 
 
 
 
Objetivos Específicos: 

 
1. Descrição do Problema 
2. Metodologia Utilizada 
3. Resultados Obtidos   
4. Conclusões   
5.Bibliotecas Utilizadas 
 

                                                                                                                                #Blue Horizon 



##1. Descrição do Problema 

A conservação da vida marinha é crucial para a manutenção do equilíbrio dos ecossistemas aquáticos. Identificar espécies marinhas em risco de extinção é um passo vital para a implementação de estratégias de conservação eficazes. Este projeto visa desenvolver um modelo de aprendizado de máquina capaz de classificar espécies marinhas como "em extinção" ou "não em extinção" com base em imagens. O objetivo é auxiliar na identificação rápida e precisa dessas espécies para apoiar esforços de conservação. 

 
##2. Metodologia Utilizada 

2.1. Coleta de Dados 

Os dados utilizados neste projeto foram obtidos do Kaggle, especificamente do dataset "Sea Animals Image Dataset" disponível aqui. O dataset foi baixado e extraído para uso no treinamento e validação do modelo. 

2.2. Pré-processamento dos Dados 

O pré-processamento dos dados incluiu as seguintes etapas: 

Rescale: As imagens foram normalizadas para o intervalo [0, 1]. 

Augmentação de Dados: Foram aplicadas técnicas de augmentação de dados para aumentar a variedade das imagens de treinamento, incluindo rotação, deslocamento, cisalhamento, zoom e inversão horizontal. 

2.3. Construção do Modelo 

Foi utilizada uma rede neural convolucional (CNN) devido à sua eficácia comprovada em tarefas de classificação de imagens. O modelo foi construído com a seguinte arquitetura: 

Camadas Convolucionais: Três camadas convolucionais com filtros de tamanhos 32, 64 e 128, respectivamente, cada uma seguida por uma camada de pooling. 

Camada de Flatten: Para achatar as ativações em um vetor unidimensional. 

Camadas Densas: Uma camada densa com 512 neurônios e função de ativação ReLU, seguida de uma camada de saída com um neurônio e função de ativação sigmoide para a classificação binária. 

2.4. Treinamento do Modelo 

O modelo foi compilado com o otimizador Adam e a função de perda de entropia cruzada binária. Durante o treinamento, foram utilizados callbacks para checkpoint e early stopping, garantindo que o modelo fosse salvo apenas quando a performance melhorasse e interrompendo o treinamento se a validação não melhorasse por um número específico de épocas. 

2.5. Avaliação do Modelo 

A avaliação do modelo foi realizada utilizando os dados de validação, medindo a acurácia e a perda durante o treinamento. As métricas de performance foram visualizadas para analisar o comportamento do modelo. 
 



##3. Resultados Obtidos 

3.1. Treinamento do Modelo 

O modelo foi treinado por várias épocas até que o early stopping interrompesse o processo. As curvas de acurácia e perda para os dados de treinamento e validação foram geradas para monitorar o desempenho do modelo. 

3.2. Desempenho do Modelo 

Acurácia de Treinamento: A acurácia do modelo nos dados de treinamento foi alta, indicando que o modelo conseguiu aprender bem as características das imagens de treino. 

Acurácia de Validação: A acurácia nos dados de validação foi ligeiramente inferior à de treinamento, sugerindo que o modelo pode ter começado a sob reajustar. 

Perda de Treinamento e Validação: A perda de treinamento e validação diminuiu de forma consistente, confirmando que o modelo estava aprendendo. 

3.3. Previsão em Imagens Novas 

A função de previsão foi testada em novas imagens, e o modelo foi capaz de classificar corretamente se a espécie estava em extinção ou não com base na imagem fornecida. 

 
 
 
 
 
##4. Conclusões 

O projeto demonstrou a viabilidade de usar redes neurais convolucionais para classificar espécies marinhas em extinção com base em imagens. O uso de técnicas de augmentação de dados, juntamente com uma arquitetura de CNN bem projetada, resultou em um modelo robusto com boa performance em dados de validação. 

Principais Conclusões: 

Efetividade das CNNs: As CNNs se mostraram eficazes para a tarefa de classificação de imagens de espécies marinhas. 

Augmentação de Dados: A augmentação de dados foi crucial para melhorar a generalização do modelo. 

Necessidade de Mais Dados: Para melhorar ainda mais o desempenho, seria benéfico ter mais dados de treinamento, especialmente para classes minoritárias. 

Futuras Direções: 

Expansão do Dataset: Coletar mais imagens de espécies marinhas, especialmente as menos representadas, para melhorar a generalização do modelo. 

Aprimoramento do Modelo: Explorar arquiteturas de modelos mais complexas e técnicas de regularização para reduzir o sob reajuste. 
 
Integração com Aplicações de Conservação: Integrar o modelo em aplicativos móveis ou sistemas de monitoramento para ajudar biólogos e conservacionistas na identificação rápida de espécies em campo. 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
##5.Bibliotecas Utilizadas: 

 

TensorFlow: 

tensorflow as tf: Estrutura principal para construir, treinar e salvar modelos de aprendizado de máquina. 

tensorflow.keras.preprocessing.image import ImageDataGenerator: Ferramentas para gerar imagens aumentadas em tempo real durante o treinamento do modelo. 

tensorflow.keras.models import Sequential: Permite a construção de um modelo sequencial, que é uma pilha linear de camadas. 

tensorflow.keras.layers import Conv2D, MaxPooling2D, Flatten, Dense: Camadas específicas usadas na construção de redes neurais convolucionais (CNNs). 

tensorflow.keras.models import load_model: Função para carregar um modelo treinado salvo. 

tensorflow.keras.preprocessing import image: Ferramentas para carregar e processar imagens para previsão. 

NumPy: 

numpy as np: Biblioteca para computação numérica em Python, oferecendo suporte para arrays e matrizes multidimensionais. 

Matplotlib: 

matplotlib.pyplot as plt: Biblioteca de plotagem em 2D, usada para criar gráficos e visualizações. 

zipfile: 

import zipfile: Biblioteca padrão do Python para manipulação de arquivos ZIP, usada para descompactar o dataset baixado. 

os: 

import os: Biblioteca padrão do Python para interação com o sistema operacional, usada para manipulação de diretórios e arquivos. 
