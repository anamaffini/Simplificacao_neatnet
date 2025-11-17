# Simplificação de Redes Viárias com NeatNet

Este repositório contém um conjunto de ferramentas para **simplificar redes viárias** utilizando o algoritmo **NeatNet**, uma biblioteca de código aberto desenvolvida para produzir representações geométricas mais limpas e consistentes de redes urbanas.

O objetivo principal é transformar redes de ruas provenientes do OpenStreetMap, QGIS ou bases oficiais em versões mais simplificadas e adequadas para análises espaciais, morfológicas, configuracionais ou topológicas.

Inclui dois componentes principais:

- **Script para QGIS** — roda diretamente como *Processing Algorithm*  
- **Notebook para VS Code / Jupyter** — fluxo reprodutível em Python para ambientes científicos

---

## 📦 Conteúdo

```
├── neatnet_simplificar_rede.py      # Script para QGIS
├── neatnet_simplify_vscode.ipynb    # Notebook Jupyter/VSCode
└── README.md                        # Este arquivo
```

---

## 🧠 O que é o NeatNet?

O **NeatNet** é uma biblioteca Python que realiza **simplificação topológica e geométrica** de redes de ruas.  
Ele resolve:

- duplicações de pistas (dual carriageways)  
- microsegmentos criados por interseções artificiais  
- ruído geométrico de importações OSM  
- variações pequenas de geometria que atrapalham análises  
- complexidade exagerada em redes de segmentos  

O resultado é uma rede **mais limpa, contínua e coerente**, ideal para:

- análises morfológicas  
- space syntax e centralidades  
- simulações urbanas  
- métricas topológicas  
- visualização estrutural da malha urbana  

---

## 🚀 Como usar no QGIS

### Instalação do script

1. Abra QGIS → **Processamento → Caixa de Ferramentas**  
2. Vá em **Scripts → Scripts de processamento → Gerenciar scripts…**  
3. Clique em **Abrir pasta de scripts**  
4. Cole o arquivo:

```
neatnet_simplificar_rede.py
```

5. Em *Scripts*, clique com o botão direito → **Recarregar scripts**

O algoritmo aparecerá como:

> **Simplificação e Morfologia Urbana → Simplificação de rede viária (neatnet)**

### Parâmetros

- **Entrada:** camada de linhas representando segmentos da rede viária  
- **Saída:** arquivo GeoPackage, Shapefile ou GeoJSON com a rede simplificada  

---

## 🧪 Uso no Jupyter Notebook / VS Code

Abra:

```
neatnet_simplify_vscode.ipynb
```

O notebook inclui:

- instalação das dependências  
- leitura da rede (GeoPackage/Shapefile/GeoJSON)  
- checagem e reprojeção de CRS  
- aplicação de `neatnet.neatify`  
- visualização da rede antes/depois  
- exportação em GeoPackage e GeoParquet  

### Trecho de configuração:

```python
DATA_DIR = r"C:\caminho\para\dados"
IN_FILE = DATA_DIR / "rede_segmentos.gpkg"
OUT_FILE = DATA_DIR / "rede_segmentos_simplificada_neatnet.gpkg"
```

---

## 🔧 Dependências

Requer:

- `geopandas`  
- `pyogrio`  
- `shapely`  
- `neatnet`  
- `matplotlib`  

### Instalação via pip

```bash
pip install geopandas pyogrio shapely neatnet
```

### Instalação via conda (recomendado)

```bash
conda install -c conda-forge geopandas pyogrio shapely numba networkx
pip install neatnet
```

---

## ⚠️ Sobre instalação no QGIS

O ambiente Python do QGIS é sensível a instalações via `pip`, especialmente para pacotes como:

- NumPy  
- Numba  
- Shapely  
- GeoPandas  

Se ocorrerem erros como *“Windows fatal exception: access violation”*, recomenda-se:

- usar um ambiente Python **externo** (Anaconda/Miniconda) para rodar o notebook  
- deixar o QGIS apenas para **visualização** e **edição SIG**

---

## 📘 Licença

Inclua aqui sua licença preferida (ex.: MIT, BSD, GPL).

---

## ✨ Autoria

**Ana Luisa Maffini**  
Urbanista e pesquisadora de morfologia urbana, redes viárias e análises espaciais.

## Citar

Maffini, A. L. (2025). Simplificação Neatnet. Zenodo. https://doi.org/10.5281/zenodo.17635086

