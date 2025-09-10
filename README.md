# Projeto de Transfer Learning – Cats vs Dogs 🐱🐶

## 📌 Descrição

Este projeto faz parte de um desafio de **Deep Learning** com **Transfer Learning**, proposto pela DNC/DIO.
O objetivo é aplicar **Transfer Learning** em uma rede neural pré-treinada para classificar imagens em **duas classes**.

Neste caso, utilizamos o dataset **Cats vs Dogs** do TensorFlow, e o modelo **VGG16** pré-treinado no **ImageNet**.

---

## 📂 Estrutura do Projeto

```
projeto-transfer-learning/
├── transfer_learning_dnc.ipynb   # Notebook com todo o código
├── README.md                     # Explicação do projeto
```

---

## 🔬 O que é Transfer Learning?

Transfer Learning é uma técnica de **aprendizado profundo** em que utilizamos uma rede neural já treinada em um grande dataset (como o ImageNet) e reaproveitamos esse conhecimento para resolver outro problema semelhante.

➡️ Em vez de treinar uma rede do zero (o que exige milhões de imagens e muito poder computacional), nós **congelamos os pesos da rede pré-treinada** e **adicionamos novas camadas finais** para a nossa tarefa específica.

---

## 📊 Dataset

* Dataset utilizado: **Cats vs Dogs**
* Fonte: [TensorFlow Datasets](https://www.tensorflow.org/datasets/catalog/cats_vs_dogs)
* Classes:

  * **0 → Gato** 🐱
  * **1 → Cachorro** 🐶

---

## 🧠 Modelo Utilizado

* **Base**: VGG16 (pré-treinada no ImageNet, sem as camadas finais).

* **Camadas adicionadas**:

  * `GlobalAveragePooling2D()`
  * `Dense(128, activation='relu')`
  * `Dropout(0.5)`
  * `Dense(1, activation='sigmoid')`

* **Função de perda**: `binary_crossentropy`

* **Otimização**: `Adam`

* **Métrica**: `accuracy`

---

## 🚀 Como Rodar o Projeto

1. Abra o [Google Colab](https://colab.research.google.com/).
2. Faça upload do notebook `transfer_learning_dnc.ipynb`.
3. Certifique-se de que o runtime está configurado para **GPU**:

   * Menu → Runtime → Change runtime type → GPU.
4. Execute as células em ordem.

   * O dataset será baixado automaticamente.
   * O modelo será treinado em algumas épocas.
5. Ao final, você verá a acurácia e os gráficos de treino/validação.

---

## 📈 Resultados

* Acurácia no conjunto de validação: **\~85% a 90%** (dependendo das épocas e da GPU do Colab).
* Curvas de treino mostram boa convergência sem necessidade de muitas épocas.

---
