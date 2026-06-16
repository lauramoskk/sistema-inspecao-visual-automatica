# Sistema de inspeção visual automática

## Criando o ambiente virtual

No terminal, dentro da pasta do projeto:

```bash
python -m venv venv
venv\Scripts\activate
```

---

## Instalação das dependências

Após ativar o ambiente virtual:

```bash
pip install -r requirements.txt
```

---

## Dataset

O dataset utilizado neste projeto pode ser obtido em:

[https://www.kaggle.com/datasets/richardradli/fruit-recognition](https://www.kaggle.com/datasets/sriramr/fruits-fresh-and-rotten-for-classification)

Após o download:

1. Extraia o arquivo `.zip`
2. Renomeie a pasta para `dataset` (caso necessário)
3. Coloque a pasta na raiz do projeto

> **Observação:** Durante os testes foi identificado que, após a extração, o dataset pode vir com uma estrutura contendo uma pasta `dataset` dentro de outra pasta `dataset`. Como ambas continham os mesmos arquivos, foi mantida apenas uma delas para evitar caminhos duplicados. Antes de executar os notebooks, verifique se a estrutura está conforme o exemplo abaixo.

```text
projeto/
│
├── dataset/
│   └── test/
│       ├── freshapples/
│       ├── freshbanana/
│       ├── freshoranges/
│       └── ...
│   └── train/
│       ├── freshapples/
│       ├── freshbanana/
│       ├── freshoranges/
│       └── ...
├── notebooks/
│
└── outputs/
```

---

## Ordem de execução

Os notebooks devem ser executados nesta ordem:

### 1. Segmentação

```text
01_segmentacao.ipynb
```

Responsável por:

- Carregar as imagens
- Aplicar segmentação
- Salvar imagens segmentadas
- Gerar classes.csv

---

### 2. Extração de Features

```text
02_features.ipynb
```

Responsável por:

- Extrair características de forma
- Extrair características de cor
- Extrair características de textura
- Gerar X.csv e y.csv

---

### 3. Classificação

```text
03_classificacao.ipynb
```

Responsável por:

- Treinar Random Forest
- Treinar SVM
- Calcular métricas
- Gerar gráficos e matrizes de confusão

---

## Arquivos gerados

Ao final da execução serão criados:

```text
outputs/
├── segmented_images/
├── classes.csv
├── X.csv
├── y.csv
├── confusion_matrix_rf.png
├── confusion_matrix_svm.png
├── tabela_metricas.csv
├── feature_importance.csv
└── top_features.png
└── validacao_cruzada.csv
```
