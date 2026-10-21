# 04 — Validation

Validação rigorosa do modelo com **Quality Gates** baseados em métricas de crédito.

## Notebooks

| # | Notebook | Objetivo |
|---|---|---|
| 1 | `01_validacao_quality_gates.ipynb` | Avalia AUC mínimo (≥ 0.70), KS test e aprova/reprova o modelo para deploy |

## Critérios de Aprovação
- **AUC** ≥ 0.70
- **KS statistic** adequado para score de crédito

## Dependências
- `scikit-learn`, `scipy`
