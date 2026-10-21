# 🧠 Estudos Databricks — Pipeline MLOps com Agentes

Repositório de estudos práticos com **Databricks**, **MLflow**, **LangGraph** e boas práticas de **MLOps**.  
O projeto simula um pipeline completo de Data Science para score de crédito comportamental, orquestrado por um agente autônomo.

---

## 🗂️ Estrutura do Projeto

```
estudos_databricks/
│
├── 00_dados_artificiais/        # ⚠️ Ingestão: geração dos dados sintéticos (executar primeiro)
├── 02_feature_engineering/      # Transformação de features e split de dados
├── 03_training/                 # Treinamento com tuning de hiperparâmetros (Optuna + XGBoost)
├── 04_validation/               # Quality Gates: AUC, KS e validação rigorosa
├── 05_deployment/               # Registro no Unity Catalog e deploy via MLflow
├── 06_monitoring/               # Monitoramento de Data Drift (PSI) e Teste A/B
├── 07_agents/                   # Agente autônomo LangGraph que orquestra o pipeline
│
├── docs/                        # Documentação adicional e diagramas
├── .gitignore
├── requirements.txt
└── README.md
```

---

## 🔄 Fluxo do Pipeline

```
00 Dados Artificiais (ingestão)
    └─► 02 Feature Engineering
            └─► 03 Training (Optuna + XGBoost + MLflow)
                    └─► 04 Validation (AUC / KS Quality Gates)
                            └─► 05 Deployment (Unity Catalog Registry)
                                    └─► 06 Monitoring (PSI Drift + Teste A/B)

07 Agents ── orquestra todas as etapas acima de forma autônoma (LangGraph)
```

---

## 📁 Detalhamento das Pastas

### `00_dados_artificiais/`
> Pasta separada para geração dos dados sintéticos. Execute-a **antes de qualquer outra etapa**.

| Notebook | Descrição |
|---|---|
| `01_setup_catalogo_unity_catalog.ipynb` | Criação do catálogo, schemas e tabelas no Unity Catalog |
| `02_geracao_dados_medalhao.ipynb` | Geração de dados sintéticos com arquitetura Medalhão (Bronze → Silver → Gold) |

### `02_feature_engineering/`
| Notebook | Descrição |
|---|---|
| `01_feature_engineering.ipynb` | Transformação de features, encoding e split treino/teste |

### `03_training/`
| Notebook | Descrição |
|---|---|
| `01_treinamento_hyperparameter_tuning.ipynb` | Tuning com Optuna + treinamento XGBoost + logging MLflow |

### `04_validation/`
| Notebook | Descrição |
|---|---|
| `01_validacao_quality_gates.ipynb` | Quality Gates: AUC mínimo, KS test e aprovação do modelo |

### `05_deployment/`
| Notebook | Descrição |
|---|---|
| `01_registro_deploy_modelo.ipynb` | Registro do modelo no Unity Catalog e deploy no serving endpoint |

### `06_monitoring/`
| Notebook | Descrição |
|---|---|
| `01_monitoramento_data_drift.ipynb` | Cálculo de PSI para detecção de Data Drift em produção |
| `02_teste_ab.ipynb` | Configuração de Teste A/B com distribuição de tráfego via SDK Databricks |

### `07_agents/`
| Notebook | Descrição |
|---|---|
| `01_agente_pipeline_mlops.ipynb` | Definição do agente LangGraph com todas as ferramentas do pipeline |
| `02_fluxo_agente.ipynb` | Execução e demonstração do fluxo autônomo do agente |
| `03_agente_catalogo.ipynb` | Agente para interação com o catálogo de dados |

---

## 🛠️ Tecnologias

| Tecnologia | Uso |
|---|---|
| **Databricks** | Plataforma principal (Unity Catalog, Serving, SDK) |
| **MLflow** | Rastreamento de experimentos e registro de modelos |
| **XGBoost** | Modelo de score de crédito |
| **Optuna** | Otimização de hiperparâmetros |
| **LangGraph** | Orquestração do agente autônomo |
| **PySpark** | Processamento distribuído de dados |
| **Scikit-learn** | Métricas e pré-processamento |

---

## ⚡ Como Executar

1. **Configure o ambiente Databricks** (cluster com Unity Catalog habilitado)
2. **Execute os notebooks em ordem**, da pasta `01_` até `07_`
3. Para rodar o pipeline completo via agente, execute `07_agents/02_fluxo_agente.ipynb`

---

## 📋 Requisitos

Veja [`requirements.txt`](requirements.txt) para as dependências Python.
