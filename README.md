# PS-Panda
Análise Exploratória de Dados (AED) sobre os fatores que influenciam o desempenho acadêmico e o consumo de álcool em estudantes, utilizando Pandas e Seaborn.

# Análise de Desempenho Estudantil e Consumo de Álcool

## 📝 Resumo do Projeto

Este projeto consiste em uma Análise Exploratória de Dados (AED) detalhada sobre o dataset "Student Alcohol Consumption" da UCI. O objetivo principal foi investigar os fatores demográficos, sociais e de hábitos que impactam o desempenho acadêmico e o consumo de álcool em estudantes do ensino secundário em Portugal.

A análise segue um fluxo completo, desde a preparação e limpeza dos dados até a engenharia de atributos, visualização e interpretação dos resultados para responder a perguntas de negócio específicas.

## 📊 O Conjunto de Dados

* **Nome:** Student Alcohol Consumption 
* **Fonte:** [Kaggle - Student Alcohol Consumption Dataset](https://www.kaggle.com/datasets/uciml/student-alcohol-consumption/data)
* **Descrição:** O dataset contém dados de estudantes das disciplinas de Matemática e Português de duas escolas portuguesas (Gabriel Pereira e Mousinho da Silveira). As informações foram coletadas via questionários e relatórios escolares.
* **Estrutura:** A análise partiu de dois arquivos `.csv` (`student-mat.csv` e `student-por.csv`) , que foram unificados e tratados, resultando em um dataset final com **662 alunos únicos** e 33 atributos.

## 🛠️ Metodologia e Etapas da Análise

O projeto foi estruturado seguindo as melhores práticas de uma Análise Exploratória de Dados:

1.  **Unificação e Limpeza de Dados:** O desafio inicial foi combinar os dois datasets, tratando os alunos que cursavam ambas as matérias. Isso foi resolvido através da **agregação inteligente** de suas notas e hábitos para criar um perfil único por estudante, evitando a perda de informações. O notebook também inclui a verificação de ruídos e outliers.

2.  **Engenharia de Atributos:** Para uma análise mais rica, novas variáveis foram criadas:
    * `alcool_total`: Uma pontuação ponderada (`5 * Dalc + 2 * Walc`) que representa o consumo de álcool semanal de forma mais realista.
    * `passed`: Uma variável binária ('Sim'/'Não') para classificar o aluno como aprovado ou reprovado com base na nota final (`G3 >= 10`).
    * Variáveis Discretizadas: `faixa_etaria`, `faixa_faltas`, e `desempenho_final` foram criadas para agrupar dados contínuos e facilitar a visualização de padrões.

3.  **Análise Descritiva e Visualização:** Foram realizadas análises univariada e bivariada para entender a distribuição dos dados e investigar as relações entre as variáveis, utilizando gráficos como `countplot`, `boxplot`, `violinplot` e `heatmap` para dar suporte visual às descobertas.

## 🔍 Principais Perguntas e Descobertas

A análise foi guiada por três perguntas centrais, e as principais descobertas foram:

#### 1. Qual a relação entre o consumo de álcool e o desempenho acadêmico?
* **Resposta:** Confirmamos uma **correlação negativa clara**. Alunos com desempenho "Insuficiente" apresentaram um consumo de álcool ponderado significativamente maior do que aqueles com desempenho "Bom" ou "Excelente".

#### 2. Como o estilo de vida social e os hábitos (sair, faltar) se conectam com o desempenho?
* **Resposta:** Identificamos um **"efeito em cadeia"**. Uma vida social mais ativa (`goout`) está diretamente ligada a um maior consumo de álcool e a um maior número de faltas (`absences`). Por sua vez, o número de faltas mostrou ter um impacto devastador nas notas, onde a faixa de "Muitas Faltas" é quase inteiramente composta por alunos com desempenho insuficiente.

#### 3. Quais os outros fatores mais determinantes para o sucesso acadêmico?
* **Resposta:** O **histórico de reprovações (`failures`)** é o preditor negativo mais forte do desempenho final. Por outro lado, fatores positivos incluem a **educação dos pais (`Medu`, `Fedu`)** e a **aspiração do aluno em continuar os estudos (`higher`)**, que mostraram correlações mais fortes do que o suporte educacional direto (como aulas pagas).

## 🚀 Ferramentas Utilizadas

* **Linguagem:** Python 3
* **Bibliotecas:** Pandas, NumPy, Matplotlib, Seaborn, Kagglehub 
* **Ambiente:** Jupyter Notebook (Google Colab)

## ⚙️ Como Executar

1.  Clone este repositório:
    ```bash
    git clone https://github.com/JoaoVitorAzevedo/PS-Panda.git
    ```
2.  Instale as dependências necessárias.
    ```bash
    pip install pandas numpy matplotlib seaborn kagglehub
    ```
3.  Abra o notebook `students-alcohol-consumption.ipynb` em um ambiente Jupyter. O notebook utiliza a biblioteca `kagglehub` para baixar os dados diretamente da fonte, garantindo a reprodutibilidade.
4.  Execute as células em ordem para reproduzir a análise.

## 👥 Autores

* [João Vitor Azevedo](https://github.com/JoaoVitorAzevedo)
* [Luísa Tavares dos Santos](https://github.com/Asiuly)
