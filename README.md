# 🧠 Inteligência Artificial Aplicada à Esclerose Múltipla: Preditores de Progressão e Estilo de Vida

Este projeto de Ciência de Dados utiliza **Machine Learning** para investigar as complexas interações entre fatores clínicos, ambientais e de estilo de vida na progressão da Esclerose Múltipla (EM).

## 📌 Objetivo do Projeto
Desenvolver e comparar modelos de aprendizado de máquina capazes de identificar padrões combinados que levam à evolução da incapacidade (escala EDSS). O foco não é apenas a precisão da previsão, mas a **interpretabilidade** dos fatores que influenciam cada paciente.

---

## 📂 Estrutura da Investigação

### 🔬 Capítulo 1: Preditores Clínicos (Kaggle)
Foco em dados históricos e biológicos. O desafio aqui é entender como variáveis do passado do paciente (como amamentação e histórico de viroses) interagem para prever a conversão para EM e a progressão da incapacidade.
* **Modelo:** Classificação Supervisionada (Random Forest / XGBoost).
* **Foco de ML:** Identificar interações não-lineares entre variáveis clínicas.

### 🌿 Capítulo 2: Estilo de Vida e Ambiente (Zenodo - BRAINTEASER)
Integração de dados externos e comportamentais (qualidade do ar, atividade física e estresse).
* **Modelo:** Modelagem de Séries Temporais e Classificação.
* **Foco de ML:** Medir o peso de fatores modificáveis (estilo de vida) versus fatores não-modificáveis (clima/poluição).

---

## 🤖 Pipeline de Machine Learning
1.  **Limpeza e Pré-processamento:** Tratamento de *missing data* em prontuários médicos e normalização de escalas.
2.  **Engenharia de Atributos (Feature Engineering):** Criação de indicadores de progressão e índices inflamatórios baseados na literatura médica.
3.  **Treinamento:** Aplicação de algoritmos robustos a dados desbalanceados.
4.  **Interpretabilidade (XAI):** Uso de **SHAP (SHapley Additive exPlanations)** para "abrir a caixa-preta" dos modelos e entender o peso de cada combinação de fatores.

---

## 🛠️ Stack Tecnológica
* **Linguagem:** Python 3.x
* **Análise de Dados:** Pandas, NumPy.
* **Visualização:** Seaborn, Matplotlib.
* **Machine Learning:** Scikit-Learn, XGBoost, SHAP.
* **Interface:** VS Code & Jupyter Notebook.

---

## 📈 Status do Projeto
- [x] Definição do escopo e criação do repositório.
- [x] Configuração do ambiente local no VS Code.
- [ ] Limpeza inicial e Análise Exploratória (EDA) - **[EM ANDAMENTO]**
- [ ] Treinamento do primeiro modelo de Classificação.
- [ ] Análise de importância de variáveis com SHAP.

---
**Nota:** Este é um projeto de pesquisa acadêmica e portfólio de dados. As previsões geradas não devem ser utilizadas para decisões médicas sem consulta a um especialista.