# 🌾 Análise Exploratória da Base Agrofit (MAPA)

> Análise de dados dos produtos formulados registrados no sistema Agrofit do Ministério da Agricultura (MAPA), com foco em ingredientes ativos, classes de uso, perfil toxicológico e presença de produtos biológicos no mercado brasileiro.

![Python](https://img.shields.io/badge/Python-3.9+-blue)
![Pandas](https://img.shields.io/badge/Pandas-1.5+-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📊 Sobre o projeto

Este projeto realiza uma **análise exploratória de dados (EDA)** da base pública de **produtos formulados do Agrofit**, disponibilizada pelo MAPA. O objetivo é extrair insights sobre:

- Concentração de mercado por empresa titular
- Distribuição de produtos por classe de uso (herbicidas, fungicidas, inseticidas, etc.)
- Ingredientes ativos mais presentes
- Perfil toxicológico e ambiental dos produtos
- Presença de produtos microbiológicos e biológicos

---

## 🗂️ Estrutura do repositório

```
📁 agrofit-analise/
│
├── 📁 data/               # Dados brutos e processados
│   └── agrofitprodutosformulados.csv
│
├── 📁 notebooks/          # Jupyter Notebooks com análises
│   └── agrofit.ipynb
│
├── 📁 outputs/            # Gráficos, tabelas e relatórios que serão gerados
│
├── README.md              # Este arquivo
└── requirements.txt       # Dependências do projeto
```

---

## 🛠️ Tecnologias utilizadas

- **Python 3.14**
- **Pandas** – manipulação e limpeza de dados
- **Jupyter Notebook** – ambiente de análise interativa

---

## 📥 Como reproduzir este projeto

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/Analise-Agrofit.git
cd Analise-Agrofit
```

### 2. Instale as dependências

```bash
pip install -r requirements.txt
```

### 3. Execute o notebook

```bash
jupyter notebook notebooks/agrofit.ipynb
```

---

## 🔍 Principais insights encontrados

### 🏢 Concentração de mercado

- As **top 10 empresas** concentram **~37% dos produtos registrados.**
- **Empresas como **Syngenta, UPL, Adama, Nortox e Sumitomo** dominam o mercado.**

### 🌿 Distribuição por classe de uso

- **~33% dos produtos** são **herbicidas**, refletindo o modelo agrícola brasileiro extensivo.
- **Inseticidas** representam **~19%** (considerando combinações).
- **~18% dos produtos** são **microbiológicos ou biológicos** — sinal positivo para alternativas sustentáveis.

### 🧪 Ingredientes ativos mais versáteis

- **Azoxistrobina + Difenoconazol** aparece em **124 culturas diferentes** — o ingrediente ativo mais versátil.
- **Difenoconazol isolado** atende **120 culturas**.

### ⚠️ Perfil toxicológico

- **~78% dos produtos** são classificados como **Categoria 4 (Pouco Tóxico)** ou **Categoria 5 (Improvável de Causar Dano)**.
- Aproximadamente **100%** dos produtos biológicos caem nessas categorias mais seguras, ou não são classificados.
- **~92% dos herbicidas** caem na classificação de **Categoria 4 e 5**.
- Inseticidas têm o perfil mais perigoso de todos, com **~28%** nas **Categorias de 1 a 3**.

---

## 🧹 Desafios enfrentados e soluções adotadas

### 1. **Duplicação de registros por cultura/alvo**

**Problema:** Cada produto aparece múltiplas vezes (uma por cultura autorizada).
**Solução:** Deduplicação por `NR_REGISTRO` antes de contar produtos únicos.

### 2. **Classes combinadas (ex: "Acaricida/Inseticida")**

**Problema:** Dificulta contagem por classe individual.
**Solução:** Análise dupla — com e sem `.explode()` para diferentes perspectivas.

### 3. **Inconsistência na coluna de classe toxicológica**

**Problema:** Mistura de sistema antigo (I-IV) e novo (Categorias 1-5), valores mal formatados.
**Solução:** Mapeamento manual e padronização com dicionário.

---

## 🚀 Próximos passos

- [ ] Continuação das análises sobre toxicologia
- [ ] Análise dos produtos biológicos
- [ ] Insights sobre as culturas atendidas e formulações
- [ ] Dashboard interativo com Plotly/Dash ou Streamlit

---

## 📚 Referências

- [Agrofit - Sistema de Agrotóxicos Fitossanitários (MAPA)](https://agrofit.agricultura.gov.br/)
- [Documentação Pandas](https://pandas.pydata.org/docs/)

---

## 👤 Autor

**[Luan Vinícius]**
📧 [luanvinicius@pm.me](mailto:luanvinicius@pm.me)
💼 [LinkedIn](https://www.linkedin.com/in/luan-vinicius-silva-dias/)
🐙 [GitHub](https://github.com/luan-vsd)

---

## 📄 Licença

Este projeto está sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 🙏 Agradecimentos

- Ao **MAPA** pela disponibilização pública dos dados.
- À comunidade open-source de Python/Pandas.
- A todos que contribuíram com feedback e revisões.
