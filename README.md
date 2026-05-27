# TP1 - Organização e Recuperação da Informação (ORI)

Este repositório contém a implementação do **Trabalho Prático 1 (TP1)** da disciplina de Organização e Recuperação da Informação. O objetivo principal do projeto é realizar o processamento de textos, extração de vocabulário e a construção de vetores de *Bag of Words* (BoW).

## 👥 Integrantes do Grupo

* Aleff
* Eduardo Lopes
* Gabriel de Oliveira

## 🎯 Objetivos do Projeto

O trabalho está estruturado em duas etapas principais, desenvolvidas em um arquivo Jupyter Notebook (`.ipynb`):

### 1. Geração de Vocabulário
* **Entrada:** Um arquivo de texto bruto.
* **Processamento:** O código lê o arquivo, converte todas as letras para minúsculas, remove pontuações e limpa a acentuação (utilizando a biblioteca `unidecode`). Em seguida, isola as palavras únicas.
* **Saída:** Um arquivo de texto contendo os termos de indexação (vocabulário) ordenados em ordem alfabética.

### 2. Representação Bag of Words (BoW)
* **Entrada:** O arquivo de vocabulário gerado na etapa 1 e um arquivo de texto representando um documento qualquer.
* **Processamento:** O algoritmo mapeia o documento contra o vocabulário de referência.
* **Saída:** Um vetor binário (ex: `[0, 1, 1, 0, ...]`) indicando a presença (`1`) ou ausência (`0`) de cada termo do vocabulário dentro do documento analisado.

## 🛠️ Tecnologias e Ferramentas

* **Linguagem:** Python 3
* **Ambiente:** Jupyter Notebook (executado via VS Code)
* **Controle de Versão:** Git / GitHub
* **Dependências:** `unidecode` (tratamento de caracteres especiais)
