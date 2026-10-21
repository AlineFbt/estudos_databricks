# 07 — Agents

Agente autônomo baseado em **LangGraph** que orquestra todo o pipeline de MLOps.

## Notebooks

| # | Notebook | Objetivo |
|---|---|---|
| 1 | `01_agente_pipeline_mlops.ipynb` | Define o agente LangGraph com as ferramentas de cada etapa do pipeline |
| 2 | `02_fluxo_agente.ipynb` | Executa e demonstra o fluxo autônomo completo do agente |
| 3 | `03_agente_catalogo.ipynb` | Agente para interação e consulta no catálogo de dados |

## Fluxo do Agente
```
feature_engineering → hyperparameter_tuning → validation → deploy → monitoring
```

O agente toma decisões em cada etapa e pode re-executar steps com base nos resultados.

## Dependências
- `langgraph`, `langchain`, `mlflow`, `xgboost`, `optuna`, `databricks-sdk`
