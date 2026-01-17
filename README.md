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
│   └── produtos_formulados.csv
│
├── 📁 notebooks/          # Jupyter Notebooks com análises
│   └── analise_exploratoria.ipynb
│
├── 📁 outputs/            # Gráficos, tabelas e relatórios gerados
│   ├── top_empresas.png
│   ├── distribuicao_classes.png
│   └── heatmap_classes_empresas.png
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

### 3. Baixe a base de dados
Acesse o site do [Agrofit (MAPA)](https://dados.agricultura.gov.br/pt_BR/dataset/sistema-de-agrotoxicos-fitossanitarios-agrofit/resource/d30b30d7-e256-484e-9ab8-cd40974e1238#) e baixe o arquivo CSV de **Produtos Formulados** mais recente.

Coloque o arquivo na pasta `data/`.

### 4. Execute o notebook
```bash
jupyter notebook notebooks/agrofit.ipynb
```

---

## 🔍 Principais insights encontrados

### 🏢 Concentração de mercado
- As **top 10 empresas** concentram **37,2%** dos produtos registrados.
- Empresas como **Syngenta, UPL, Adama, Nortox e Sumitomo** dominam o mercado.

### 🌿 Distribuição por classe de uso
- **33,7% dos produtos** são **herbicidas**, refletindo o modelo agrícola brasileiro extensivo.
- **Inseticidas** representam ~19% (considerando combinações).
- **~18% dos produtos** são **microbiológicos ou biológicos** — sinal positivo para alternativas sustentáveis.

### 🧪 Ingredientes ativos mais versáteis
- **Azoxistrobina + Difenoconazol** aparece em **124 culturas diferentes** — o ingrediente ativo mais versátil.
- **Difenoconazol isolado** atende **120 culturas**.

### ⚠️ Perfil toxicológico
- **~78% dos produtos** são classificados como **Categoria IV (Pouco Tóxico)** ou **Categoria V (Improvável de Causar Dano)**.
- Produtos biológicos geralmente caem nessas categorias mais seguras.

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
