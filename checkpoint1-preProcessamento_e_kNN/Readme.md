## 🐱🐶🐾 CHECKPOINT 1 — Classificador de Raças: Pomeranian, Egyptian Mau, Ragdoll e Shiba Inu usando k-NN

Treinamento de um **classificador multiclasse** de raças utilizando o algoritmo k-NN (k-nearest neighbors). O modelo é capaz de identificar a raça presente em uma imagem dentre as seguintes opções:

- 🐕 **Pomeranian**
- 🐈 **Egyptian Mau**
- 🐈 **Ragdoll**
- 🐕 **Shiba Inu**

---

## 📌 Objetivos

- Treinar um classificador k-NN capaz de identificar imagens pertencentes a **quatro raças distintas** de gatos e cachorros.
- Utilizar o k-NN com diferentes técnicas de **extração de características**: **HOG** e **CNNs**.
- Selecionar as **seis melhores bases**, aplicar **PCA** e treinar novamente o classificador para verificar os efeitos da redução de dimensionalidade.

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **NumPy** e **Pandas** (manipulação de dados)
- **Matplotlib** (visualização)
- **Scikit-Learn** (métricas de avaliação, k-NN, PCA)

---

## 📚 Base de Dados

Foi utilizado um **subconjunto** da base pública **Oxford-IIIT Pet Dataset**:

- Fonte oficial: [https://www.robots.ox.ac.uk/~vgg/data/pets/](https://www.robots.ox.ac.uk/~vgg/data/pets/)
- Contém imagens rotuladas de **37 raças** de gatos e cães.
- Para este checkpoint, foram selecionadas **apenas 4 raças**: **Pomeranian**, **Egyptian Mau**, **Ragdoll** e **Shiba Inu**.

---

## ✅ Sobre este checkpoint

Este checkpoint teve como foco testar e avaliar o desempenho do classificador k-NN. Nas **6 melhores bases**, com base na acurácia, foi aplicada a técnica de **PCA** para verificar a viabilidade e o impacto da redução de dimensionalidade.

### 📌 Modelos Treinados

- **k-NN** (K-Nearest Neighbors)

Cada modelo foi treinado utilizando um **dataframe** gerado a partir de diferentes configurações de **extratores de características**:

- **HOG** (Histogram of Oriented Gradients)
- **CNNs**: **VGG16** e **VGG19** (pré-treinadas)

Esses extratores transformaram as imagens em **vetores representativos**, adequados para o treinamento dos modelos clássicos.

---

## 🐾 Bases HOG

As bases HOG foram criadas a partir de diferentes parâmetros de padronização das imagens e de pixels por célula:

- **Padronização de imagens:** 128x128 e 256x256 pixels
- **Pixels por célula:** 16x16 e 20x20

Totalizando **4 bases HOG**.

---

## 🐾 Bases CNN

As bases CNN foram formadas com diferentes parâmetros de padronização e pooling:

- **Padronização de imagens:** 128x128 e 256x256 pixels
- **Pooling:** Max e Avg pooling

Totalizando **8 bases CNN**.

---

## 📉 Redução de Dimensionalidade

- Aplicação de **PCA** (Análise de Componentes Principais) nas **6 melhores bases** do classificador k-NN, para reduzir a dimensionalidade e verificar se a aplicação dessa técnica melhora ou prejudica o desempenho.

---

## 📁 Estrutura do Projeto

- `/Notebooks`  
  → Scripts para extração de características com **HOG** e **CNNs** pré-treinadas, treinamento com **k-NN** e redução de dimensionalidade com **PCA** nas 6 melhores bases.

- `/Relatório`  
  → Documento com a descrição dos experimentos realizados, resultados obtidos e observações sobre o primeiro checkpoint.

---

## 📊 Resultados

Os resultados incluem:

- **Acurácia**
- **Matriz de confusão**
- **Gráficos comparativos** de desempenho entre os modelos, considerando os diferentes extratores de características e a aplicação do PCA.

---

## ✍️ Autores

- Luiz Felipe de Souza Silva
