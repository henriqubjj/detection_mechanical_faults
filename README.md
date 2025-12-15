# Detecção de Falhas Mecânicas com MAFAULDA

## Objetivo

Desenvolver uma solução para detecção de falhas mecânicas utilizando o banco de dados MAFAULDA, composto por séries temporais multivariadas de sensores em diferentes condições de operação (normal e desbalanceamento).

## Etapas do Projeto

### 1. Importação e Organização dos Dados

- Todos os arquivos CSV das classes "normal" e "imbalance" foram carregados e concatenados.
- Cada classe foi identificada por um rótulo (target), permitindo a classificação supervisionada.
- O downsampling foi aplicado para reduzir o volume de dados e viabilizar o processamento.

### 2. Análise Exploratória

- Foram analisadas estatísticas descritivas, distribuição dos dados, autocorrelação, estacionariedade e espectro de frequência.
- Visualizações mostraram padrões distintos entre as classes, com sinais periódicos e diferenças de amplitude/frequência.
- A análise confirmou a presença de autocorrelação e não-normalidade em parte dos dados.

### 3. Pré-processamento

- Aplicou-se padronização (z-score) para igualar a escala dos sensores.
- O split dos dados foi feito antes da padronização para evitar data leakage.
- O dataset final foi balanceado entre as classes.

### 4. Escolha, Treinamento e Validação dos Modelos

- Dois modelos foram escolhidos: Random Forest e LightGBM, ambos robustos para classificação multiclasse e dados correlacionados.
- Os modelos foram treinados e validados com validação cruzada (5-fold), garantindo avaliação justa e sem overfitting.

### 5. Avaliação dos Resultados

- As métricas de acurácia, F1-score e matriz de confusão foram utilizadas para comparar os modelos.
- O LightGBM apresentou desempenho ligeiramente superior ao Random Forest, distiguindo niveis proximos.
- O Random Forest também obteve resultados robustos, sendo uma alternativa confiável para o problema.

## Conclusão

O pipeline desenvolvido permite identificar falhas mecânicas a partir de séries temporais de sensores, com etapas justificadas e resultados robustos. O uso de downsampling, padronização e validação cruzada garantiu eficiência e confiabilidade. O LightGBM foi o modelo com melhor desempenho neste cenário, mas o Random Forest também se mostrou uma alternativa sólida para classificação de falhas mecânicas.
