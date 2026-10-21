# 00 — Dados Artificiais

Geração dos dados sintéticos usados em todo o pipeline. Esses notebooks **simulam a ingestão de dados reais** e devem ser executados primeiro.

## Notebooks

| # | Notebook | Tipo | Objetivo |
|---|---|---|---|
| 1 | `01_setup_catalogo_unity_catalog.ipynb` | Dados sintéticos | Cria catálogo, schemas e tabelas no Unity Catalog |
| 2 | `02_geracao_dados_medalhao.ipynb` | Dados sintéticos | Gera dados de crédito sintéticos (Bronze → Silver → Gold) |
| 3 | `03_ingestao_bacen_sgs.ipynb` | **Dados externos** | API SGS/Bacen — inadimplência, juros e comprometimento de renda |
| 4 | `04_ingestao_rfb_cnpj_qsa.ipynb` | **Dados externos** | Receita Federal — CNPJ, QSA (sócios), MEI, capital social e situação cadastral |

## Séries Ingeridas do Banco Central (SGS)

| Código | Série | Uso |
|---|---|---|
| `21127` | Inadimplência — Cartão Rotativo (PF) | Proxy de risco do mercado |
| `21128` | Inadimplência — Cartão Parcelado (PF) | Proxy de risco de parcelamento |
| `21114` | Inadimplência — Crédito Pessoal Não Consignado | Benchmark de inadimplência livre |
| `21116` | Inadimplência — Crédito Pessoal Consignado (Privado) | Benchmark consignado |
| `29034` | Comprometimento de Renda das Famílias (SFN Total) | Proxy de stress financeiro |
| `29035` | Comprometimento de Renda (exceto habitacional) | Proxy de stress no consumo |

## ⚠️ Pré-requisito
Execute esta pasta **antes de qualquer outra**. Os demais notebooks dependem das tabelas geradas aqui.

## Dependências
- PySpark (nativo no Databricks)
- Unity Catalog habilitado no workspace
