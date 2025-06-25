# 🐱🐶🐾 Classificador de Raças: Pomeranian, Egyptian Mau, Ragdoll e Shiba Inu

Projeto de **Aprendizado de Máquina** com foco na **classificação multiclasse de raças**. O modelo é capaz de identificar a raça presente em uma imagem dentre as seguintes opções:

- 🐕 **Pomeranian**
- 🐈 **Egyptian Mau**
- 🐈 **Ragdoll**
- 🐕 **Shiba Inu**

---

## 📌 Objetivos

- Treinar modelos capazes de classificar imagens em **4 raças distintas** de gatos e cachorros.
- Explorar diferentes **extratores de características de imagens**: **HOG** e **CNNs**.
- Avaliar e comparar o desempenho dos modelos utilizados em cada **checkpoint**.

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **TensorFlow** | **Keras**
- **NumPy** e **Pandas**
- **Matplotlib** (visualização)
- **Scikit-Learn** (métricas de avaliação, modelos de treinamento e pré-processamento)

---

## 📚 Base de Dados

Utilizou-se um **subconjunto** da base pública **Oxford-IIIT Pet Dataset**:

- Fonte oficial: [https://www.robots.ox.ac.uk/~vgg/data/pets/](https://www.robots.ox.ac.uk/~vgg/data/pets/)
- Contém imagens rotuladas de **37 raças** de gatos e cães.
- Para este projeto, foram selecionadas **apenas 4 raças**: **Pomeranian**, **Egyptian Mau**, **Ragdoll** e **Shiba Inu**.

---

## ✅ Checkpoints

Em cada **checkpoint** foi designada uma atividade para **teste e avaliação** do modelo de treinamento.

### 📌 Modelos treinados:

- **k-NN** (K-Nearest Neighbors)
- **Árvore de Decisão**
- **Naive Bayes**
- **Redes Neurais**

Cada modelo foi treinado utilizando um **dataframe** construído a partir de diferentes configurações dos **extratores de características**:

- **HOG** (Histogram of Oriented Gradients)
- **CNNs**: **VGG16** e **VGG19** (pré-treinadas)

Esses extratores foram aplicados nas imagens para transformá-las em **vetores representativos**, adequados para o treinamento dos modelos clássicos e das redes neurais.

### 📉 Redução de Dimensionalidade:

- Aplicação de **PCA** (Análise de Componentes Principais) para reduzir a dimensionalidade das características extraídas, melhorando a eficiência dos modelos.

---

## 📁 Estrutura do Projeto

- `/checkpoint1-preProcessamento_e_kNN`  
  → Pré-processamento das imagens, extração de características com **HOG** e **CNNs** pré-treinadas, treinamento com **k-NN** e redução de dimensionalidade com **PCA** nas 6 melhores bases.

- `/checkpoint2_NB_DT`  
  → Treinamento e análise com **Árvore de Decisão** e **Naive Bayes**.

---

## 🚀 Como rodar o projeto

1. Clone o repositório:  
   `git clone <url-do-repositório>`

2. Instale as dependências:  
   `pip install -r requirements.txt`

3. Execute os notebooks ou scripts dentro de cada pasta de **checkpoint** conforme o fluxo de testes desejado.

---

## 📊 Resultados

Os resultados incluem a **acurácia**, **matriz de confusão** e gráficos comparativos de desempenho entre os modelos, considerando diferentes extratores de características e técnicas de redução de dimensionalidade.

---

## ✍️ Autores

- Luiz Felipe de Souza Silva

