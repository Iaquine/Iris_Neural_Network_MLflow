
# Classificação do Dataset Iris com Redes Neurais e MLflow

Este projeto demonstra como aplicar MLOps utilizando o MLflow em um problema clássico de classificação: o dataset **Iris**. Em vez de modelos de visão computacional, usamos **Redes Neurais (MLPClassifier)** adequadas para dados tabulares.

## Visão Geral

O dataset Iris contém informações sobre três espécies de flores com base em características como:
- Comprimento e largura da sépala
- Comprimento e largura da pétala

Cada linha do dataset representa uma flor. O objetivo é prever a espécie da flor com base nessas características.

## Principais Componentes

- **Modelo**: Multi-Layer Perceptron (MLPClassifier) do scikit-learn.
- **MLflow**: Para rastreamento de experimentos e salvamento de artefatos.
- **Matriz de Confusão**: Usada como visualização dos resultados.
- **Relatório de Classificação**: Registrado como artefato de texto.

## Capturas de Tela

### Interface do MLflow com Execuções
![Experimentos MLflow](Captura%20de%20Tela%202025-06-28%20às%2016.11.32.png)

### Logs do Terminal com Resultados
![Execução no Terminal](Captura%20de%20Tela%202025-06-28%20às%2016.12.23.png)

## Como Executar

1. **Instale as dependências:**

```bash
pip install pandas scikit-learn seaborn matplotlib mlflow
```

2. **Execute o código Python ou Notebook** com o experimento (como `Projeto_2_Iris_Neural_Network_MLflow.ipynb`).

3. **Inicie a interface do MLflow:**

```bash
mlflow ui
```

4. **Acesse no navegador:**
```
http://localhost:5000
```

5. **Analise os Resultados:**
- Navegue até o experimento `Classificacao_Iris_RedeNeural`
- Veja os detalhes dos "runs"
- Acesse os artefatos gerados, como:
  - `matriz_confusao.png`
  - `classification_report.txt`


## Estrutura de Código (Resumo)

- Carregamento do dataset com `load_iris()`
- Split entre treino/teste
- Treinamento de redes com arquiteturas como:
  - `(50,)`, `(100,)`, `(50, 50)`, `(100, 50, 25)`
- Log de métricas, parâmetros e artefatos com MLflow

## Considerações

Durante o treinamento, alguns modelos podem apresentar o aviso de que não convergiram completamente (`ConvergenceWarning`). Isso indica que o número de iterações pode ser aumentado.

Para cada execução, foram gerados:
- Acurácia da arquitetura
- Matriz de Confusão
- Relatório de Classificação
- Modelo registrado no MLflow

---

Este projeto demonstra como adaptar pipelines de MLOps para redes neurais em dados tabulares, focando na rastreabilidade e análise visual dos modelos.

