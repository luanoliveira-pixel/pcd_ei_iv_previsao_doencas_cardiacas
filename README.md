# Previsão de Doença Cardíaca com KNN

Projeto aplicado da disciplina **Programação para Ciência de Dados**.

**Integrantes:** Gustavo Kulbaba, Luan de Oliveira e Victor Weizenmann

## Problema

A partir de exames clínicos simples (idade, pressão, colesterol, eletrocardiograma, teste de esforço), prever se um paciente tem doença cardíaca. É um problema de classificação binária.

## Dados

- **Base:** Heart Disease, Cleveland Clinic ([UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/45/heart+disease))
- **Tamanho:** 303 pacientes, 14 variáveis
- **Leitura:** CSV carregado direto por URL com `pd.read_csv`. Há uma cópia em `dados/heart.csv`

## Etapas

1. Obtenção dos dados
2. Limpeza: remoção da coluna de índice, renomeação, remoção de 6 linhas com valores ausentes, alvo em 0/1
3. Análise exploratória com Pandas e Matplotlib
4. Preparação: one-hot encoding (`get_dummies`), divisão treino/teste 80/20 e padronização (`StandardScaler`)
5. Escolha do k do KNN por validação cruzada (5 partes)
6. Treino do modelo final e avaliação no teste
7. Demonstração com um paciente

## Resultados

| Métrica (teste) | Valor |
|---|---|
| Melhor k | 21 |
| Acurácia na validação cruzada | 82,2% |
| Acurácia no teste | 85,0% |
| Recall (com doença) | 78,6% |
| Precision (com doença) | 88,0% |

Sem padronização, a acurácia cai para cerca de 65%, o que mostra que essa etapa é essencial para o KNN.

## Estrutura do repositório

```
.
├── README.md
├── doenca_cardiaca_knn.ipynb
├── dados/
│   └── heart.csv
└── docs/
    └── Relatório Técnico - Projeto Integrador em Grupo.pdf
    └── Relatório Técnico - Projeto Integrador em Grupo.docx
    └── PCD - EI IV - Previsão de Doenças Cardíacas.pdf
```

## Como executar

1. Abra o notebook no Google Colab (Arquivo > Abrir notebook > GitHub, e cole o link do repositório).
2. Clique em **Ambiente de execução > Executar tudo**.

Não é preciso instalar nada: o Colab já tem pandas, numpy, matplotlib e scikit-learn.

## Bibliotecas

- pandas
- numpy
- matplotlib
- scikit-learn
