#  Inteligência Artificial Aplicada à Esclerose Múltipla: Preditores de Progressão e Estilo de Vida

Neste projeto de Ciência de Dados, eu utilizo **Machine Learning** para investigar as complexas interações entre fatores clínicos, ambientais e de estilo de vida na progressão da Esclerose Múltipla (EM).

##  Meu Objetivo
Desenvolver modelos de aprendizado de máquina capazes de prever se a doença de um paciente vai progredir (avaliado pela piora na escala EDSS). O meu foco não foi apenas alcançar uma alta precisão matemática ilusória, mas sim focar no **Recall** (sensibilidade) e na **interpretabilidade** dos fatores que disparam os surtos, provando que o estilo de vida é a chave para a medicina preventiva.

---

##  A Jornada dos Dados e Conclusões

### Capítulo 1: O Limite dos Preditores Clínicos (Dados do Kaggle)
Iniciei a investigação utilizando dados clínicos reais, históricos e biológicos de pacientes, obtidos de forma anonimizada no Kaggle.
* **O que eu fiz:** Realizei a limpeza profunda dos dados (*missing data*), evitei o vazamento de dados (*Data Leakage*) e criei o meu alvo de predição comparando o EDSS inicial e final.
* **O Desafio:** Encontrei um desbalanceamento severo, onde mais de 90% dos pacientes estavam estáveis.
* **A Conclusão do Capítulo 1:** Treinei um modelo *Random Forest* e esbarrei no "Paradoxo da Acurácia". A IA tirou nota 92% no geral, mas teve **Recall de 0.00** para os pacientes graves (não detectou ninguém que piorou). Com isso, provei matematicamente que apenas o histórico biológico e exames de rotina não contam a história toda da doença. Faltavam os "gatilhos".

###  Capítulo 2: O Poder do Estilo de Vida (Dados Sintéticos)
Como dados reais que cruzam saúde com fatores ambientais (como os do projeto europeu BRAINTEASER) possuem barreiras estritas de privacidade médica (LGPD/GDPR), eu construí a minha própria **Fábrica de Dados Sintéticos** (Mock Data), embasada rigorosamente na literatura médica atual.
* **O que eu fiz:** Simulei 500 pacientes incluindo variáveis cruciais: Tabagismo, Níveis de Vitamina D, Estresse, Poluição do Ar, Qualidade do Sono e Poliautoimunidade (presença de outras doenças autoimunes).
* **A Descoberta dos Gatilhos:** Através de uma Análise de Correlação (Mapa de Calor), o algoritmo identificou sozinho que o **Tabagismo (0.32)**, a **Poliautoimunidade (0.18)** e o **Estresse (0.16)** eram os maiores vilões da progressão, enquanto a Vitamina D e o Exercício funcionavam como escudos.
* **A Conclusão do Capítulo 2:** Treinei um novo modelo focado nestes hábitos de vida e apliquei a técnica de **SMOTE** para balancear os dados. A IA finalmente "acordou": o Recall subiu para **0.33**. 
* **O Trade-off Médico:** A IA aumentou os Falsos Positivos (classificando pacientes estáveis como casos de risco). Em negócios, isso é um problema; na medicina, **é o cenário ideal**. Aumentei a sensibilidade porque o custo de mandar um paciente grave para casa sem tratamento (Falso Negativo) é infinitamente pior do que pedir exames preventivos extras (Falso Positivo).

---

## Pipeline de Machine Learning
1. **Limpeza e Pré-processamento:** Tratamento de *missing data* e remoção de colunas que causavam vazamento de resposta.
2. **Geração de Dados Sintéticos:** Criação de *Mock Data* estruturada para contornar restrições de privacidade médica.
3. **Engenharia de Atributos:** Criação da variável alvo `Houve_Progressao` baseada em regras de negócios clínicas.
4. **Balanceamento de Classes:** Uso extensivo de **SMOTE (Synthetic Minority Over-sampling Technique)** para criar clones virtuais de pacientes graves e ensinar a IA a focar na minoria. 
5. **Treinamento e Avaliação:** Uso do *Random Forest Classifier* e foco absoluto na interpretação da **Matriz de Confusão** e na métrica de **Recall** (Sensibilidade).

---

##  Stack Tecnológica
* **Linguagem:** Python 3.x
* **Análise e Manipulação de Dados:** Pandas, NumPy.
* **Visualização:** Seaborn, Matplotlib.
* **Machine Learning:** Scikit-Learn (Random Forest), Imbalanced-Learn (SMOTE).
* **Ambiente:** VS Code & Jupyter Notebook.

---

## Status do Projeto
- [x] Definição do escopo e criação do repositório.
- [x] Configuração do ambiente local no VS Code.
- [x] Limpeza de dados e Análise Exploratória (EDA) com Mapa de Calor.
- [x] Detecção da falha dos preditores clínicos isolados (Capítulo 1).
- [x] Geração de dados simulados de estilo de vida baseados na literatura (Capítulo 2).
- [x] Treinamento do modelo final de Classificação com SMOTE focado no aumento de Recall médico.
- [ ] Deploy do modelo em uma interface web (Próximos passos opcionais).

---
**Nota Ética:** Este é um projeto de pesquisa acadêmica, portfólio de Ciência de Dados e Engenharia de Software. As previsões e dados gerados (mesmo que embasados em literatura) não devem ser utilizados para decisões diagnósticas sem a supervisão e consulta de um médico neurologista especialista.