# Esteira de Aprendizado de Máquina – Heart Disease

## 1. Sobre o projeto

Este projeto tem como objetivo desenvolver uma esteira de aprendizado de máquina utilizando Python, contemplando desde a preparação e transformação dos dados até o treinamento, a avaliação e a realização de previsões individuais.

Foi desenvolvido um modelo de classificação capaz de identificar, com base nas informações dos pacientes, se o registro apresenta ou não indícios de doença cardíaca, utilizando o algoritmo **Random Forest**.

O projeto foi desenvolvido como atividade acadêmica individual.

## 2. Dataset utilizado

Foi utilizado o conjunto de dados **Heart Disease**, disponibilizado pela Universidade da Califórnia em Irvine (UCI Machine Learning Repository).

- **Nome:** Heart Disease – Cleveland
- **Fonte:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/45/heart+disease)
- **Arquivo utilizado:** `processed.cleveland.data`
- **Quantidade de registros:** 303
- **Quantidade de atributos:** 14

A base contém informações clínicas dos pacientes, como idade, sexo, tipo de dor no peito, pressão arterial, colesterol e frequência cardíaca máxima.

A variável `num` representa a classificação original da presença de doença cardíaca. Para o projeto, ela foi transformada em uma variável binária:

- `0`: Ausência de doença cardíaca.
- `1`: Presença de doença cardíaca.

## 3. Tecnologias e bibliotecas utilizadas

O projeto foi desenvolvido em Python, utilizando o Google Colab para execução do notebook.

As principais bibliotecas utilizadas foram:

| Tecnologia | Finalidade |
|---|---|
| Python | Linguagem de programação |
| Google Colab | Ambiente de desenvolvimento e execução |
| Pandas | Carregamento, manipulação e análise dos dados |
| NumPy | Operações numéricas |
| Scikit-learn | Pré-processamento, divisão dos dados, treinamento e avaliação do modelo |
| Matplotlib | Visualização da matriz de confusão |
| Zipfile e OS | Extração e localização dos arquivos |

## 4. Etapas da esteira de aprendizado de máquina

A esteira foi organizada em 11 etapas:

1. **Extração dos arquivos:** extração do arquivo ZIP e identificação do conjunto de dados utilizado.
2. **Carregamento dos dados:** leitura do arquivo CSV e definição dos nomes das 14 colunas.
3. **Análise exploratória:** verificação das informações gerais, tipos de dados, valores ausentes e estatísticas descritivas.
4. **Transformação e limpeza:** conversão da variável-alvo para classificação binária, verificação de duplicidades e embaralhamento dos registros.
5. **Divisão dos dados:** separação em treinamento (70%), validação (15%) e teste (15%), utilizando estratificação para manter a proporção das classes.
6. **Pré-processamento:** preenchimento de valores ausentes, padronização das variáveis numéricas e codificação das variáveis categóricas.
7. **Treinamento:** configuração e treinamento do algoritmo Random Forest, utilizando 300 árvores de decisão.
8. **Avaliação com dados de validação:** análise do desempenho do modelo durante o desenvolvimento.
9. **Avaliação com dados de teste:** avaliação final utilizando registros que não participaram do treinamento.
10. **Matriz de confusão:** visualização dos acertos e erros nas classificações.
11. **Previsão individual:** utilização de um registro para demonstrar uma previsão realizada pelo modelo e suas probabilidades estimadas.

O pré-processamento e o classificador foram integrados em uma única estrutura utilizando `Pipeline` e `ColumnTransformer`, organizando as etapas da esteira e evitando que o pré-processamento utilize informações dos conjuntos de validação e teste durante o treinamento.

## 5. Resultados obtidos

Após o treinamento e a avaliação, foram obtidos os seguintes resultados:

| Avaliação | Acurácia |
|---|---:|
| Validação | 86,67% |
| Teste | 76,09% |

No conjunto de teste, o modelo acertou **35 das 46 classificações realizadas**.

### Matriz de confusão

| Classificação real / prevista | Sem doença | Com doença |
|---|---:|---:|
| Sem doença | 18 | 7 |
| Com doença | 4 | 17 |

A matriz demonstra que o modelo classificou corretamente 18 registros sem doença e 17 registros com doença, totalizando 35 acertos.

### Previsão individual

Também foi realizada uma previsão utilizando um registro individual do conjunto de teste.

O resultado apresentado pelo modelo foi:

- **Classificação:** Ausência de doença cardíaca.
- **Probabilidade estimada de ausência de doença:** 70%.
- **Probabilidade estimada de presença de doença:** 30%.

Essas probabilidades representam estimativas produzidas pelo modelo e não devem ser interpretadas como diagnóstico médico ou avaliação clínica de risco.

## 6. Como reproduzir a execução

Para reproduzir a execução apresentada no vídeo, siga os passos abaixo.

### Pré-requisitos

- Uma conta Google para acessar o Google Colab.
- O notebook Python (`.ipynb`) disponibilizado neste repositório.
- Conexão com a internet para acessar o dataset.

### Passo 1 – Acessar o Google Colab

Acesse [Google Colab](https://colab.research.google.com/) e faça login com sua conta Google.

### Passo 2 – Abrir o notebook

No Google Colab, selecione a opção de upload e envie o arquivo `.ipynb` disponível neste repositório.

### Passo 3 – Baixar o dataset

Acesse o [UCI Machine Learning Repository – Heart Disease](https://archive.ics.uci.edu/dataset/45/heart+disease) e faça o download do conjunto de dados.

Utilize o arquivo ZIP disponibilizado pela plataforma, mantendo seu nome como `heart+disease.zip`.

### Passo 4 – Enviar o dataset para o Colab

No ambiente do Google Colab:

1. Abra a aba de arquivos, localizada na lateral esquerda.
2. Clique na opção de upload.
3. Envie o arquivo `heart+disease.zip`.

O notebook espera encontrar o arquivo no caminho `/content/heart+disease.zip`. Caso o arquivo seja salvo em outro local ou tenha outro nome, ajuste o caminho no primeiro bloco de código.

### Passo 5 – Executar o notebook

Com o notebook e o dataset disponíveis, execute os blocos de código na ordem apresentada, desde a extração dos arquivos até a previsão individual.

A execução pode ser realizada pelo botão **Executar tudo** ou individualmente, utilizando o botão de execução de cada célula.

### Passo 6 – Conferir os resultados

Ao finalizar a execução, serão apresentados:

- Informações e estatísticas do conjunto de dados.
- Quantidade de registros e distribuição das classes.
- Divisão dos dados em treinamento, validação e teste.
- Resultado do treinamento do Random Forest.
- Acurácia e relatório de classificação da validação e do teste.
- Matriz de confusão.
- Exemplo de previsão individual com probabilidades estimadas.

Os resultados esperados são aproximadamente 86,67% de acurácia na validação e 76,09% no teste, considerando a mesma base de dados, configuração e `random_state` utilizados no notebook.

## 7. Considerações finais

O desenvolvimento deste projeto permitiu aplicar, na prática, as principais etapas de uma esteira de aprendizado de máquina, desde a preparação dos dados até a avaliação de um modelo de classificação.

A utilização do Random Forest apresentou resultados satisfatórios para a atividade proposta, demonstrando como técnicas de aprendizado de máquina podem ser aplicadas à análise de dados.

**Observação:** este projeto possui finalidade exclusivamente acadêmica e demonstrativa. O modelo não deve ser utilizado para diagnósticos ou decisões médicas.
