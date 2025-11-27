# 🧠 Comparativo de Modelos de Machine Learning (Iris Dataset)

Este projeto consiste na implementação e comparação de três algoritmos clássicos de Aprendizado de Máquina Supervisionado para a classificação do dataset **Iris**. O objetivo é treinar, testar e analisar o desempenho de cada modelo.

## 📂 Estrutura do Projeto

O projeto foi dividido em notebooks separados para isolar o treinamento de cada modelo:

1.  **`1_SVM.ipynb`**: Implementação do Support Vector Machine (Kernel Linear).
2.  **`2_RandomForest.ipynb`**: Implementação do Random Forest (Ensemble).
3.  **`3_KNN.ipynb`**: Implementação do K-Nearest Neighbors (Baseado em distância).

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3
* **Ambiente:** Jupyter Notebook (VS Code)
* **Bibliotecas:**
    * `pandas`: Manipulação de dados.
    * `scikit-learn`: Algoritmos de Machine Learning e métricas.
    * `seaborn` & `matplotlib`: Visualização de dados (Matriz de Confusão).

## 🚀 Como Executar

Certifique-se de ter as dependências instaladas:


pip install pandas seaborn matplotlib scikit-learn notebook

## 📚 Funções e Conceitos Utilizados

Abaixo, detalho as principais funções e métodos do `scikit-learn` aplicados no projeto para garantir a reprodutibilidade e eficácia dos testes:

### 1. Pré-processamento de Dados
* **`load_iris()`**: Função utilitária que carrega o dataset Iris diretamente da biblioteca, contendo 150 amostras de 3 espécies de flores.
* **`train_test_split(test_size=0.3, random_state=42)`**:
    * Divide o conjunto de dados em duas partes: **70% para Treino** (aprender padrões) e **30% para Teste** (validar conhecimento).
    * O parâmetro `random_state=42` foi essencial para fixar a "semente" aleatória, garantindo que a divisão seja sempre a mesma em todas as execuções e tornando a comparação entre os modelos justa.

### 2. Modelos de Machine Learning (Instanciação)
Cada modelo foi configurado com hiperparâmetros específicos para o cenário:
* **`SVC(kernel='linear')`**: Instancia o Support Vector Machine configurado para buscar uma linha reta (hiperplano) que melhor separa as classes.
* **`RandomForestClassifier(n_estimators=100)`**: Instancia o modelo criando uma "floresta" composta por 100 árvores de decisão que votam na classificação final.
* **`KNeighborsClassifier(n_neighbors=5)`**: Instancia o algoritmo KNN configurado para observar os 5 vizinhos mais próximos antes de decidir a classe da flor.

### 3. Ciclo de Vida do Modelo
* **`.fit(X_train, y_train)`**: O método de **Treinamento**. É aqui que o algoritmo recebe os dados de estudo e ajusta seus parâmetros internos (aprende).
* **`.predict(X_test)`**: O método de **Inferência**. O modelo recebe dados novos (que nunca viu) e tenta classificar com base no que aprendeu.

### 4. Avaliação e Métricas
* **`accuracy_score()`**: Calcula a porcentagem global de acertos (ex: 0.97 significa 97% de precisão).
* **`confusion_matrix()`**: Gera uma matriz que cruza as classes reais vs. as classes preditas, permitindo ver exatamente onde o modelo errou.
* **`sns.heatmap()`**: Função da biblioteca Seaborn utilizada para transformar a matriz de confusão numérica em um mapa de calor visual, facilitando a interpretação dos erros.

```bash
