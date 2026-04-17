# Análise de Dados de Exportação do COMEX Brasil

Projeto de Trabalho de Conclusão de Curso (TCC) focado em **extração, tratamento e análise de dados históricos de exportação do COMEX (Comércio Exterior) do Brasil**, utilizando Python, Pandas e técnicas de Data Science.

---

## 📋 Sobre o Projeto

Este projeto realiza análises detalhadas sobre o desempenho das exportações brasileiras em diferentes períodos, estados e categorias de produtos. Os dados são obtidos do Sistema de Análise das Informações de Comércio Exterior (ALICE/COMEX) e submetidos a tratamento, limpeza e análises exploratórias.

### Objetivos Principais
- Extrair e consolidar dados de exportação do COMEX
- Realizar tratamento e limpeza de dados
- Gerar insights sobre padrões de exportação brasileira
- Analisar tendências por período, estado, país de destino e categoria de produto
- Documentar metodologias e resultados em artigos científicos

---

## 📁 Estrutura do Projeto

```
TCC/
├── README.md                          # Este arquivo
├── dados.json                         # Mapeamento de países (ID ↔ Nome)
├── saida_do_postman.csv              # Dados brutos de exportação
│
├── script/                            # Notebooks Python de análise
│   ├── expo_2024.ipynb               # Análise de exportações 2024
│   ├── expo_2025.ipynb               # Análise de exportações 2025
│   └── id_paises.ipynb               # Processamento de IDs de países
│
├── data/                              # Dados processados e referências
│   ├── Dados.ipynb                   # Notebook de importação de dados
│   └── hdr-data.json                 # Dados estruturados de países
│
├── Artigo/                            # Documentação e publicações
│   └── PPE_v43_n01_Produtividade.pdf # Artigo sobre produtividade
│
├── relevatamento/                     # Levantamento de dados brutos
└── Ler- ML/                           # Estudos de Machine Learning
```

---

## 📊 Descrição dos Dados

Os dados de exportação contêm as seguintes variáveis por operação:

| Campo | Descrição | Tipo |
|-------|-----------|------|
| **O_ANO** | Ano de referência da exportação | Inteiro |
| **CO_MES** | Mês de referência (01-12) | Inteiro |
| **SH4** | Código do Sistema Harmonizado (4 dígitos) | String |
| **CO_PAIS** | Código do país de destino | Inteiro |
| **SG_UF_MUN** | Sigla do Estado (UF) brasileiro | String |
| **CO_MUN** | Código do município (IBGE) | Inteiro |
| **KG_LIQUIDO** | Peso líquido em quilogramas | Float |
| **VL_FOB** | Valor em Dólares Americanos (FOB) | Float |

### Estrutura de Dados Complementares

- **dados.json** - Dicionário com 281 países/territórios (ID ↔ Nome) utilizado para enriquecer análises
- **hdr-data.json** - Dados estruturados de referência para processamento

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **Pandas** - Manipulação e análise de dados
- **Jupyter Notebook** - Ambientes interativos de análise
- **NumPy** - Operações numéricas
- **CSV & JSON** - Formatos de dados

---

## 🚀 Como Usar

### Pré-requisitos
```bash
pip install pandas pandas jupyter numpy
```

### Executar Análises

1. **Abra o Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

2. **Selecione um dos notebooks de análise:**
   - `script/expo_2025.ipynb` - Para análise mais recente
   - `script/expo_2024.ipynb` - Para comparação histórica
   - `data/Dados.ipynb` - Para importação e limpeza de dados

3. **Execute as células** para processar e visualizar os dados

### Estrutura de um Notebook de Análise

```python
# 1. Importação de bibliotecas
import pandas as pd

# 2. Carregamento dos dados
dados = pd.read_csv('EXP_2025_MUN.csv', sep=';', encoding='utf-8')

# 3. Exploração inicial
dados.head(100)
dados.info()

# 4. Limpeza e tratamento
# 5. Análises exploratórias
# 6. Visualizações
```

---

## 📈 Análises Disponíveis

### expo_2025.ipynb
- Carregamento e exploração de dados de 2025
- Estatísticas descritivas
- Análise de distribuição por:
  - Estados brasileiros (SG_UF_MUN)
  - Países de destino (CO_PAIS)
  - Categorias de produtos (SH4)
  - Períodos mensais (CO_MES)

### expo_2024.ipynb
- Comparação de tendências com dados de 2024
- Análise de variação ano a ano
- Identificação de mudanças significativas

### id_paises.ipynb
- Processamento e validação do mapeamento de países
- Enriquecimento de dados com nomes de países
- Tratamento de inconsistências

---

## 📝 Referências

- **Fonte dos dados:** Sistema ALICE/COMEX da Secretaria de Comércio Exterior
- **Artigo relacionado:** `Artigo/PPE_v43_n01_Produtividade.pdf`
- **Documentação COMEX:** [MDIC - Comércio Exterior](https://www.gov.br/produtividade-e-comercio-exterior)

---
