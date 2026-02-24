# Desafio SENAI - ICPHM23 Data Challenge

Projeto de classificação de falhas em engrenagens planetárias com sinais de vibração (eixos X, Y, Z) usando Machine Learning.

## Objetivo
Classificar 5 condições da engrenagem solar:
- 0: Normal
- 1: Surface Wear
- 2: Crack
- 3: Chipped
- 4: Tooth Missing

## Estrutura do projeto
- `ICPHM23_Data_Challenge.ipynb`: notebook principal com pipeline completo.
- `Rotação 1500/` e `Rotação 2700/`: dados brutos em `.npy`.
- `model_1500.pkl` e `model_2700.pkl`: modelos treinados.
- `scaler_1500.pkl` e `scaler_2700.pkl`: scalers salvos.
- `resultados.pdf`: material de resultados.

## Pipeline (resumo)
1. Carregamento dos dados por condição operacional (1500 e 2700 rpm).
2. EDA (distribuição de classes e visualização de sinais).
3. Extração de features no tempo e na frequência.
4. Normalização com `StandardScaler`.
5. Avaliação de múltiplos modelos com validação cruzada estratificada (5-fold).
6. Treino final com separação treino/teste (80/20) e análise de métricas.
7. Salvamento dos modelos e scalers.

## Requisitos
- Python 3.10+
- Jupyter Notebook

Bibliotecas principais:
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scipy`
- `scikit-learn`

## Como executar
1. Abra o arquivo `ICPHM23_Data_Challenge.ipynb`.
2. Execute as células em ordem (de cima para baixo).
3. Confira as saídas de métricas, matrizes de confusão e gráficos.

## Reprodutibilidade
- O projeto usa `random_state=42` nas etapas principais de treino/validação.
- Arquivos grandes (`.npy` e `.pkl`) são versionados com Git LFS.

## Observações
- O notebook inclui uma função para predição em novos sinais: `predict_fault(...)`.
- Os modelos finais foram treinados separadamente para cada condição operacional.
