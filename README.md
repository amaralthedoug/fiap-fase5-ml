# 🌾 FarmTech Solutions — Análise de Rendimento de Culturas com ML

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-orange?logo=scikit-learn&logoColor=white)
![FIAP](https://img.shields.io/badge/FIAP-2026-red?logo=academia&logoColor=white)

Este projeto apresenta uma análise completa de **rendimento de culturas agrícolas** utilizando técnicas avançadas de Machine Learning. Desenvolvido como parte do programa de Inteligência Artificial da FIAP (Fase 5), o notebook explora dados climáticos e agronômicos para prever o rendimento de diferentes culturas através de modelos supervisionados e não supervisionados, oferecendo insights valiosos para otimização da produção agrícola.

---

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Dataset](#-dataset)
- [Metodologia](#-metodologia)
- [Principais Resultados](#-principais-resultados)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Como Executar](#-como-executar)
- [Visualizações](#-visualizações)
- [Comparação de Custos AWS](#-comparação-de-custos-aws)
- [Autor](#-autor)
- [Licença](#-licença)

---

## 🎯 Sobre o Projeto

O projeto **FarmTech Solutions** utiliza aprendizado de máquina para analisar e prever o rendimento de culturas agrícolas com base em variáveis climáticas. O objetivo é fornecer insights baseados em dados que possam auxiliar agricultores e gestores agrícolas na tomada de decisões estratégicas.

### Objetivos Principais

- 📊 **Análise Exploratória**: Compreender distribuições, correlações e padrões nos dados climáticos
- 🔍 **Clustering**: Identificar grupos de condições climáticas similares usando aprendizado não supervisionado
- 🤖 **Predição de Rendimento**: Treinar e comparar múltiplos modelos de regressão para prever o rendimento de culturas
- 📈 **Feature Importance**: Identificar quais variáveis climáticas mais impactam o rendimento

---

## 📁 Estrutura do Projeto

```
fiap-fase5-ml/
├── Douglas_rm566740_pbl_fase5.ipynb  # Notebook principal com análise completa
├── crop_yield.csv                     # Dataset de rendimento de culturas
├── README.md                          # Este arquivo
├── figures/                           # Visualizações geradas
│   ├── 01_distribuicoes.png          # Histogramas das variáveis
│   ├── 02_boxplots.png               # Boxplots para detecção de outliers
│   ├── 03_correlacao.png             # Matriz de correlação
│   ├── 04_rendimento_por_cultura.png # Rendimento por tipo de cultura
│   ├── 05_elbow_kmeans.png           # Método do cotovelo (K-Means)
│   ├── 06_clusters_pca.png           # Visualização de clusters (PCA)
│   ├── 07_modelo1_actual_vs_pred.png # Predição vs Real (Linear Regression)
│   ├── 08_feature_importance.png     # Importância das features (Random Forest)
│   └── aws_comparison.html           # Comparação de custos AWS
└── reports/                           # Relatórios estatísticos
```

---

## 📊 Dataset

O dataset `crop_yield.csv` contém **156 observações** de diferentes culturas agrícolas com as seguintes variáveis:

| Variável | Descrição | Unidade |
|----------|-----------|---------|
| **Cultura** | Tipo de cultura agrícola | Categórica |
| **Precipitação** | Precipitação diária | mm/dia |
| **Umidade Específica** | Umidade específica a 2 metros | g/kg |
| **Umidade Relativa** | Umidade relativa a 2 metros | % |
| **Temperatura** | Temperatura a 2 metros | °C |
| **Rendimento** | Rendimento da cultura (variável alvo) | kg/ha |

### Características do Dataset

- ✅ **Sem valores nulos**: Dataset completo e limpo
- ✅ **Múltiplas culturas**: Incluindo Cacau, Café, Mandioca e outras
- ✅ **Variáveis climáticas**: Dados abrangentes de condições ambientais

---

## 🔬 Metodologia

O projeto está estruturado em **6 seções principais**:

### 1️⃣ Setup & Imports
- Configuração do ambiente Python
- Importação de bibliotecas (pandas, scikit-learn, matplotlib, seaborn)
- Criação de diretórios para outputs
- Carregamento e validação do dataset

### 2️⃣ Análise Exploratória de Dados (EDA)
- **Distribuições**: Histogramas de todas as variáveis numéricas
- **Outliers**: Boxplots para identificação de valores atípicos
- **Correlações**: Matriz de correlação entre variáveis
- **Segmentação**: Análise de rendimento por tipo de cultura
- **Estatísticas descritivas**: Resumo completo dos dados

### 3️⃣ Clustering (Aprendizado Não Supervisionado)
- **Normalização**: StandardScaler para padronização dos dados
- **Método do Cotovelo**: Determinação do número ótimo de clusters
- **K-Means**: Agrupamento em 3 clusters distintos
- **PCA**: Redução dimensional para visualização 2D
- **Análise de Clusters**: Interpretação dos grupos identificados

### 4️⃣ Pré-processamento
- **Label Encoding**: Codificação da variável categórica 'Cultura'
- **Train-Test Split**: Divisão 80/20 para treino e teste
- **Normalização**: StandardScaler aplicado aos dados de treino e teste

### 5️⃣ Modelos de Regressão
Foram treinados e comparados **5 modelos diferentes**:

| Modelo | Algoritmo |
|--------|-----------|
| Modelo 1 | **Linear Regression** |
| Modelo 2 | **Random Forest Regressor** |
| Modelo 3 | **Gradient Boosting Regressor** |
| Modelo 4 | **Support Vector Regression (SVR)** |
| Modelo 5 | **K-Nearest Neighbors (KNN)** |

### 6️⃣ Avaliação e Conclusões
- **Métricas**: MAE, RMSE, R²
- **Comparação de Modelos**: Identificação do melhor modelo
- **Feature Importance**: Análise das variáveis mais importantes
- **Conclusões e Recomendações**: Insights e próximos passos

---

## 🏆 Principais Resultados

### Desempenho dos Modelos

| Modelo | MAE | RMSE | R² |
|--------|-----|------|-----|
| **Random Forest** ✅ | 2,744.58 | 4,656.11 | **0.9944** |
| Gradient Boosting | 3,052.78 | 5,176.01 | 0.9931 |
| K-Nearest Neighbors | 28,503.97 | 35,675.87 | 0.6719 |
| Linear Regression | 53,724.49 | 65,364.57 | -0.1015 |
| SVR | 38,973.19 | 71,312.76 | -0.3110 |

### 🥇 Melhor Modelo: Random Forest

O **Random Forest Regressor** alcançou o melhor desempenho com:
- **R² = 0.9944** (99.44% da variância explicada)
- **MAE = 2,744.58 kg/ha** (erro médio absoluto)
- **RMSE = 4,656.11 kg/ha** (raiz do erro quadrático médio)

### Feature Importance (Random Forest)

As variáveis mais importantes para predição do rendimento foram:
1. **Cultura** (tipo de cultura agrícola) - maior impacto
2. **Temperatura** - forte correlação positiva
3. **Precipitação** - influência moderada
4. **Umidade Relativa** - influência menor
5. **Umidade Específica** - menor impacto

### Insights da Análise de Clustering

- Identificados **3 clusters distintos** de condições climáticas
- Clusters representam diferentes perfis agronômicos
- Culturas com condições similares tendem a ter rendimentos comparáveis

---

## 🛠️ Tecnologias Utilizadas

### Linguagem e Ambiente
- **Python 3.12**
- **Jupyter Notebook**

### Bibliotecas Principais

#### Manipulação de Dados
- `pandas` - Análise e manipulação de dados
- `numpy` - Computação numérica

#### Visualização
- `matplotlib` - Criação de gráficos estáticos
- `seaborn` - Visualizações estatísticas avançadas
- `yellowbrick` - Visualizações de Machine Learning

#### Machine Learning
- `scikit-learn` - Modelos de ML e métricas
  - `StandardScaler`, `LabelEncoder` - Pré-processamento
  - `train_test_split` - Divisão de dados
  - `KMeans`, `PCA` - Clustering e redução dimensional
  - `LinearRegression` - Regressão linear
  - `RandomForestRegressor` - Random Forest
  - `GradientBoostingRegressor` - Gradient Boosting
  - `SVR` - Support Vector Regression
  - `KNeighborsRegressor` - K-NN
  - Métricas: `MAE`, `RMSE`, `R²`

---

## 🚀 Como Executar

### Pré-requisitos

- Python 3.12 ou superior
- pip (gerenciador de pacotes Python)

### Instalação

1. **Clone o repositório**
```bash
git clone https://github.com/amaralthedoug/fiap-fase5-ml.git
cd fiap-fase5-ml
```

2. **Crie um ambiente virtual (recomendado)**
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate     # Windows
```

3. **Instale as dependências**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn yellowbrick jupyter
```

### Execução

4. **Inicie o Jupyter Notebook**
```bash
jupyter notebook
```

5. **Abra o notebook**
   - No navegador, abra `Douglas_rm566740_pbl_fase5.ipynb`
   - Execute as células sequencialmente (Shift + Enter)

### Estrutura de Execução

O notebook está dividido em seções autocontidas. Execute na ordem:
1. Setup & Imports → Configuração inicial
2. EDA → Análise exploratória
3. Clustering → Aprendizado não supervisionado
4. Preprocessing → Preparação dos dados
5. Modelos → Treinamento e avaliação
6. Conclusões → Resultados finais

---

## 📸 Visualizações

O projeto gera **8 visualizações de alta qualidade** salvas em `figures/`:

### Análise Exploratória
- **01_distribuicoes.png**: Histogramas das 5 variáveis numéricas
- **02_boxplots.png**: Boxplots para detecção de outliers
- **03_correlacao.png**: Matriz de correlação (heatmap)
- **04_rendimento_por_cultura.png**: Distribuição de rendimento por cultura

### Clustering
- **05_elbow_kmeans.png**: Método do cotovelo para K-Means
- **06_clusters_pca.png**: Visualização dos clusters em 2D (PCA)

### Modelos de Regressão
- **07_modelo1_actual_vs_pred.png**: Valores reais vs preditos (Linear Regression)
- **08_feature_importance.png**: Importância das features (Random Forest)

Todas as figuras são salvas em **alta resolução (300 DPI)** para uso em apresentações e relatórios.

---

## ☁️ Comparação de Custos AWS

O projeto inclui uma **análise comparativa de custos de infraestrutura AWS** entre as regiões de São Paulo (Brasil) e Northern Virginia (EUA).

### 📊 Visualização Interativa

Acesse a comparação completa em: [`figures/aws_comparison.html`](figures/aws_comparison.html)

### Resumo da Comparação

| Região | Instância | Custo Mensal | Diferença |
|--------|-----------|--------------|-----------|
| **São Paulo** (sa-east-1) | t4g.micro | $17.38 USD | +71.6% |
| **N. Virginia** (us-east-1) | t4g.micro | $10.13 USD | Base |

**Diferença Mensal**: $7.25 USD (São Paulo é 71.6% mais caro)

### Por Que Escolher São Paulo?

Apesar do custo superior, a região de São Paulo oferece vantagens críticas:

✅ **Latência Reduzida**: Menor latência para usuários brasileiros
✅ **Conformidade LGPD**: Dados armazenados em território nacional
✅ **Regulamentação**: Compliance com legislação brasileira

### Especificações Técnicas (Ambas as Regiões)

- **Tipo de Instância**: t4g.micro (AWS Graviton2)
- **vCPUs**: 2 cores
- **RAM**: 1 GiB
- **Rede**: Até 5 Gbps
- **Armazenamento**: 50 GB gp3 EBS

> **Recomendação**: Para aplicações voltadas ao mercado brasileiro com requisitos de LGPD, recomenda-se a região de São Paulo apesar do custo adicional.

---

## 👨‍💻 Autor

**Douglas Rafael do Amaral**
- **RM**: 566740
- **Curso**: Inteligência Artificial
- **Instituição**: FIAP
- **Fase**: 5
- **GitHub**: [@amaralthedoug](https://github.com/amaralthedoug)
- **Email**: douglas.rafa.amaral@gmail.com

---

## 📄 Licença

Este projeto foi desenvolvido para fins educacionais como parte do programa de Inteligência Artificial da FIAP.

---

## 🙏 Agradecimentos

- **FIAP** - Pela formação em Inteligência Artificial
- **Professores e Mentores** - Pelo suporte durante a Fase 5
- **Comunidade Open Source** - Pelas bibliotecas e ferramentas utilizadas

---

<div align="center">

**Desenvolvido com ❤️ para a FIAP 2026**

[![GitHub](https://img.shields.io/badge/GitHub-amaralthedoug-181717?logo=github&logoColor=white)](https://github.com/amaralthedoug)
[![Python](https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)

</div>
