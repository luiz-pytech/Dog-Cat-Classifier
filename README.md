# 🐱🐶🐾 Classificador de Raças de Cães e Gatos

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Projeto de Aprendizado de Máquina com foco na classificação multiclasse de raças de animais de estimação. O modelo é capaz de identificar a raça presente em uma imagem dentre as seguintes opções: Pomeranian, Egyptian Mau, Ragdoll e Shiba Inu.

## Tabela de Conteúdos
- [Visão Geral](#-visão-geral)
- [Objetivos](#-objetivos)
- [Estrutura do Repositório](#-estrutura-do-repositório)
- [Metodologia](#-metodologia)
- [Tecnologias Utilizadas](#️-tecnologias-utilizadas)
- [Como Executar o Projeto](#-como-executar-o-projeto)
- [Resultados](#-resultados)
- [Autor](#️-autor)

## 🔭 Visão Geral

Este projeto explora a construção de um pipeline de Machine Learning para um problema de classificação de imagens. Partindo de um subconjunto do famoso *Oxford-IIIT Pet Dataset*, o desafio é treinar e avaliar diferentes modelos para distinguir entre quatro raças específicas, sendo duas de cães e duas de gatos:

* 🐕 **Pomeranian**
* 🐈 **Egyptian Mau**
* 🐈 **Ragdoll**
* 🐕 **Shiba Inu**

O desenvolvimento foi dividido em checkpoints, permitindo uma análise incremental do desempenho à medida que diferentes técnicas e modelos eram introduzidos, culminando em uma verificação estatística da relevância dos resultados.

## 📌 Objetivos

* Treinar modelos capazes de classificar imagens nas 4 raças distintas.
* Explorar e comparar diferentes extratores de características de imagens: **HOG** (clássico) e **CNNs** (baseado em Deep Learning).
* Avaliar e comparar o desempenho de modelos clássicos de Machine Learning, Redes Neurais e Comitês de Classificadores.
* Analisar o impacto da redução de dimensionalidade com **PCA** na performance dos modelos.
* Validar estatisticamente os resultados dos modelos com os testes de **Friedman** e **Nemenyi**.

## 📂 Estrutura do Repositório

O projeto está organizado da seguinte forma para garantir clareza e reprodutibilidade:

```
/
├── data/               # Armazena os dados brutos e processados
├── notebooks/          # Notebooks Jupyter com o passo a passo das análises
├── reports/            # Relatórios, gráficos e matrizes de confusão
├── src/                # Código fonte com funções reutilizáveis
├── README.md           # Este arquivo
└── requirements.txt    # Dependências do projeto
```

## 🔬 Metodologia

#### 1. Base de Dados
Utilizou-se um subconjunto da base pública **Oxford-IIIT Pet Dataset**.
* **Fonte oficial:** [VGG - Oxford Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/)
* **Raças selecionadas:** Pomeranian, Egyptian Mau, Ragdoll e Shiba Inu.

#### 2. Extração de Características
Para que os modelos pudessem "entender" as imagens, elas foram convertidas em vetores numéricos usando duas abordagens:
* **HOG (Histogram of Oriented Gradients):** Um extrator de características clássico que captura informações sobre formas e contornos.
* **CNNs Pré-treinadas (VGG16 e VGG19):** Utilizou-se o poder de redes neurais convolucionais já treinadas em um vasto dataset (ImageNet) para extrair características complexas e de alto nível das imagens.

#### 3. Redução de Dimensionalidade
* **PCA (Análise de Componentes Principais):** Aplicado sobre os vetores de características para reduzir sua dimensionalidade, otimizando o tempo de treinamento e, em alguns casos, melhorando a performance dos modelos.

#### 4. Modelagem e Validação
O treinamento foi dividido em etapas sequenciais, com cada notebook focando em uma parte do processo:
* **Checkpoint 1: `k-NN e PCA`**
    * Treinamento do modelo **k-NN** com as diferentes bases de características (HOG, VGG16, VGG19).
    * Avaliação do impacto do PCA nas seis melhores bases geradas pelas CNNs.
* **Checkpoint 2: `Naive Bayes e Decision Tree`**
    * Treinamento e análise dos modelos **Naive Bayes** e **Árvore de Decisão**.
* **Checkpoint 3: `Redes Neurais - MLP`**
    * Implementação e avaliação de uma rede neural **Multilayer Perceptron (MLP)**.
* **Checkpoint 4: `Comitês de Classificadores`**
    * Exploração de métodos de conjunto (*ensemble methods*): **Bagging, Boosting, Stacking, Random Forest** e **XGBoost**.
* **Checkpoint 5: `Testes Estatísticos`**
    * Aplicação dos testes de **Friedman** e **Nemenyi** para comparar estatisticamente o desempenho dos algoritmos e validar se as diferenças de performance são significativas.

## 🛠️ Tecnologias Utilizadas

* **Python 3.x**
* **TensorFlow & Keras:** Para extração de características com CNNs e modelagem com Redes Neurais.
* **Scikit-Learn:** Para modelos de ML, pré-processamento (PCA) e métricas de avaliação.
* **NumPy & Pandas:** Para manipulação de dados e vetores.
* **Matplotlib & Seaborn:** Para visualização de dados e resultados.
* **Jupyter Notebook:** Para experimentação e análise interativa.

## 🚀 Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/luiz-pytech/Classificador_Racas_gato_Cachorro.git](https://github.com/luiz-pytech/Classificador_Racas_gato_Cachorro.git)
    cd Classificador_Racas_gato_Cachorro
    ```

2.  **Crie e ative um ambiente virtual (recomendado):**
    ```bash
    python -m venv venv
    # No Windows
    .\venv\Scripts\activate
    # No macOS/Linux
    source venv/bin/activate
    ```

3.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```
    *Dica: Para gerar o `requirements.txt` atualizado, use o comando `pip freeze > requirements.txt`.*

4.  **Execute os notebooks:**
    Abra os notebooks na pasta `/notebooks`. Recomenda-se seguir a ordem definida pelos checkpoints para um entendimento completo do fluxo de trabalho.

## 📊 Resultados

Os resultados detalhados, incluindo métricas de acurácia, matrizes de confusão e os testes estatísticos, podem ser encontrados nos notebooks e nos arquivos da pasta [`/reports/`](./reports/) e figuras em [`/reports/figures`](./reports/figures) .

**Principais Conclusões:**

* **Extração de Características:** A abordagem com **CNNs pré-treinadas (VGG16/VGG19)** apresentou um desempenho significativamente superior ao **HOG**. O HOG demonstrou limitações para abstrair características robustas a variações de ângulo, iluminação e pose dos animais.

* **Desempenho dos Modelos:** Dentre os modelos individuais, a rede neural **MLP (Multilayer Perceptron)** alcançou a maior acurácia. Entre os comitês, o modelo de **Stacking** com 5 classificadores se destacou como a abordagem mais performática.

* **Impacto do PCA:** A aplicação do PCA mostrou-se muito eficaz. Além de reduzir drasticamente a dimensionalidade dos dados (otimizando o custo computacional), a técnica também levou a um aumento na acurácia da maioria dos modelos testados.

## 📊 Resultados Quantitativos

Abaixo estão as tabelas com as métricas de acurácia para cada modelo e extrator de características.

### Tabela 1: Acurácia por Modelo e Extrator de Características

| Modelo | Extrator HOG | Extrator VGG16 | Extrator VGG19 |
| :--- | :---: | :---: | :---: |
| **k-NN** | 32,86% | 95,67% | 95,67% |
| **Árvore de Decisão** | 30,21% | 91,14% | 85,73% |
| **Naive Bayes** | 45,71% | 96,56% | 96,14% |
| **MLP (Rede Neural)**| XX | 99,16 | 99,16% |

### Tabela 2: Acurácia dos Comitês de Classificadores (Ensembles)

| Comitê | Acurácia |
| :--- | :---: |
| **Random Forest** | 97,15% |
| **Bagging** | 95,97% |
| **Boosting** |92,83% |
| **Stacking** | 98% |

---

## ✍️ Autor

* **Luiz Felipe de Souza Silva**
