# 06 — Monitoring

Monitoramento do modelo em produção: **Data Drift** (PSI) e **Teste A/B** de versões.

## Notebooks

| # | Notebook | Objetivo |
|---|---|---|
| 1 | `01_monitoramento_data_drift.ipynb` | Calcula PSI entre dados de treino e produção para detectar Data Drift |
| 2 | `02_teste_ab.ipynb` | Configura distribuição de tráfego Champion/Challenger via Databricks SDK |

## Métricas
- **PSI** (Population Stability Index): threshold padrão = 0.25
- **Teste A/B**: split de tráfego configurável entre versões do modelo

## Dependências
- `numpy`, `databricks-sdk`
