# Estudo Preditivo: Otimização de Escoamento e Armazenagem (Porto Seco Roraima)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TheOneHP/artigo_ecai/blob/main/notebooks/Artigo_ECAI_v2.ipynb)

## 📋 Resumo
Este projeto aborda o desafio logístico de prever o escoamento de soja (NCM 12019000) na região amazônica, um cenário caracterizado por **Small Data** (séries temporais curtas) e alta volatilidade. O objetivo central é fornecer subsídios técnicos para a operação do futuro **Porto Seco de Roraima**, permitindo a antecipação de gargalos de escoamento e a otimização da rotatividade de carga através do cálculo do **Índice de Pressão de Escoamento (IPE)**.

## 🔬 Metodologia
A pesquisa emprega uma abordagem comparativa rigorosa entre modelos estatísticos tradicionais e arquiteturas de Deep Learning:

*   **Modelagem Clássica:** Uso de **ARIMA (AutoRegressive Integrated Moving Average)** como baseline estatístico.
*   **Deep Learning:** Implementação de **Micro-LSTM (Long Short-Term Memory)** Multivariado, otimizado para lidar com a escassez de dados típica da região.
*   **Métricas de Performance:** Avaliação via **RMSE (Root Mean Squared Error)** e **MAE (Mean Absolute Error)**. 
*   **Tratamento de Dados:** Expurgo técnico do **MAPE** em casos de valores nulos ou extremos para evitar distorções estatísticas.
*   **Validação Estatística:** Aplicação do **Teste de Diebold-Mariano** para comprovar a superioridade estatística de um modelo sobre o outro na previsão do escoamento regional.

## 📁 Estrutura do Repositório
```plaintext
previsao-escoamento-soja-rr/
│
├── data/               # Dados brutos de exportação (RR, MT, AM, PA)
│   ├── exportacoes_rr.xlsx
│   ├── exportacoes_mt.xlsx
│   ├── exportacoes_am.xlsx
│   └── exportacoes_pa.xlsx
│
├── notebooks/          # Pipeline de processamento e modelagem
│   └── Artigo_ECAI_v2.ipynb
│
├── results/            # Saídas consolidadas (CSV e Gráficos)
└── README.md           # Documentação e Vitrine Técnica
```

## 🚀 Como Executar
A forma mais simples de reproduzir os resultados é através do Google Colab:
1. Clique no botão **"Open In Colab"** no topo deste README.
2. Certifique-se de que o ambiente de execução está configurado para utilizar GPU (opcional, mas recomendado para o treinamento da LSTM).
3. Execute as células sequencialmente. O notebook instalará automaticamente as dependências necessárias (`pmdarima`, `tensorflow`, `arch`).

## ⚠️ Aviso sobre os Dados (Fallback)
Para garantir a **reprodutibilidade total** e a continuidade da pesquisa, este repositório inclui uma pasta `/data` com os arquivos `.xlsx` brutos. 
*   **Mecanismo de Fallback:** O pipeline de dados possui uma lógica de fallback. Caso a API oficial do Governo (**ComexStat**) esteja instável ou inacessível no momento da execução, o script carregará automaticamente os dados locais para processamento.

---
**Autor:** TheOneHP  
**Instituição:** Universidade Federal de Roraima (UFRR)  
**Contexto:** Artigo Científico - ECAI v2
