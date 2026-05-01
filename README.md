# TelecomX - Parte 2

Este repositório contém a segunda etapa do projeto de análise de Churn, focada na construção de modelos de Machine Learning e na definição de estratégias de retenção baseadas em dados.

## 🚀 Objetivos
- Balancear os dados para tratar o desequilíbrio de classes (Churn).
- Treinar e comparar múltiplos modelos de classificação.
- Identificar as variáveis com maior impacto na evasão.
- Propor estratégias comerciais acionáveis.

## 🛠️ Tecnologias e Técnicas
- **Balanceamento**: SMOTE (Synthetic Minority Over-sampling Technique).
- **Modelos**: KNN, Regressão Logística, Decision Tree e Random Forest.
- **Métricas de Avaliação**: Acurácia, Precisão, Recall, F1-Score e Matriz de Confusão.
- **Ajuste de Hiperparâmetros**: Controle de `max_depth` e `min_samples_leaf` para mitigar overfitting.
- **Pipeline Correto**: Split → SMOTE → Normalização, garantindo isolamento total do conjunto de teste e ausência de data leakage.

## 📊 Resultados dos Modelos

| Modelo | Acurácia (Teste) | Melhor Métrica | Status |
| :--- | :---: | :---: | :--- |
| **KNN (K=10)** | **75%** | Acurácia | **Maior Acurácia Geral** |
| Random Forest (Ajustado) | 74% | F1-Score (59%) | Melhor Equilíbrio Precisão/Recall |
| Regressão Logística | 59% | Recall (87%) | Mais conservador na detecção |
| Decision Tree (Ajustada) | 59% | Recall (73%) | Generalização básica |

> **Nota:** Para problemas de churn, o **F1-Score** é a métrica mais relevante, pois equilibra a identificação correta de clientes que vão cancelar com a minimização de falsos alarmes. Por isso, o **Random Forest** é o modelo mais indicado para uso em produção, apesar do KNN ter maior acurácia geral.

## 💡 Principais Insights
- **Contratos Mensais**: Representam o maior risco de churn.
- **Fibra Óptica**: Apresenta uma taxa de cancelamento inesperadamente alta, sugerindo necessidade de auditoria de qualidade.
- **Tenure**: Clientes nos primeiros 6 meses são os mais voláteis.

## 🎯 Estratégia de Retenção Proposta
Implementação de um plano de migração de contratos com incentivos progressivos:
- **Mensal → Anual**: 10% de desconto + 1 mês de brinde.
- **Mensal → Bianual**: 25% de desconto + 2 meses de brinde.

*Justificativa*: Redução do custo mensal (gatilho de churn) e aumento do LTV (Life Time Value) garantido.
