# Roadmap de Desenvolvimento: TP1 - ORI

Este mapa detalha o passo a passo para desenvolver o processamento de textos, extração de vocabulário e a construção dos vetores Bag of Words (BoW). Siga esta ordem lógica para estruturar o projeto.

---

## Etapa 1: Dominando a Entrada e Saída (I/O) de Arquivos
Antes de processar os dados, é necessário conseguir abri-los e salvá-los com segurança no Python.

* **O que entender:** Como a linguagem interage com o sistema de arquivos do sistema operacional.
* **O que pesquisar:**
  * `How to open and read a text file in Python open() read()`
  * `How to write to a text file in Python write()`
  * `Python "with open(...) as f:" context manager` (Essencial para fechar o arquivo automaticamente e não vazar memória).
* **Ação:** Crie um script base que apenas lê o arquivo `entrada.txt` e imprime o conteúdo na tela.

---

## Etapa 2: Limpeza e Normalização de Dados (Pré-processamento)
A etapa mais crítica. Se entrar lixo (pontuação, letras maiúsculas), o vocabulário será gerado de forma incorreta.

* **O que entender:** A padronização de "Sabiá", "sabia" e "SABIA" para uma única forma minúscula e sem acento.
* **O que pesquisar:**
  * `Python string lower() method`
  * `How to remove punctuation from a string in Python` (Pesquise sobre a biblioteca nativa `string` e `string.punctuation`, ou Expressões Regulares com `re`).
  * `How to remove accents from strings in Python unidecode`
  * `Python string replace() method` (Útil para limpar quebras de linha indesejadas `\n`).
* **Ação:** Crie uma função chamada `limpar_texto(texto_bruto)`. Ela deve receber o texto original e retornar um texto 100% em minúsculas, sem pontuações ou acentos.

---

## Etapa 3: Tokenização e Geração do Vocabulário
Nesta etapa, o texto limpo é transformado em unidades separadas (palavras) e os termos repetidos são eliminados.

* **O que entender:** O conceito de *Tokenização* e o uso de estruturas de dados focadas em elementos únicos.
* **O que pesquisar:**
  * `Python split string into list of words split()`
  * `How to remove duplicates from a list in Python using set()` (Transformar em `set` é a forma mais performática no Python para isso).
  * `How to sort a list alphabetically in Python sort() vs sorted()`
* **Ação:** Passe o texto limpo pelo `split()`, converta a lista para `set` para sumir com as repetições, converta de volta para lista, ordene alfabeticamente e salve no arquivo `saida_vocabulario.txt`.

---

## Etapa 4: Construção do Vetor Bag of Words (BoW)
A lógica principal de mapeamento. Você vai comparar o documento de entrada contra o seu vocabulário oficial recém-criado.

* **O que entender:** O modelo vetorial. O computador processará a presença dos termos através de um vetor binário `[0, 1]`.
* **O que pesquisar:**
  * `Python iterate over a list for loop`
  * `Python check if item exists in a list "in" operator`
  * `Python list append() method`
* **Ação:**
  1. Carregue o vocabulário gerado (Etapa 3) em uma lista.
  2. Carregue o novo documento e passe-o pelas funções `limpar_texto()` e `split()`.
  3. Inicie uma lista vazia: `vetor_bow = []`.
  4. Crie um *loop* que passa por cada palavra do vocabulário de referência: se a palavra existir na lista do documento, execute `vetor_bow.append(1)`. Se não existir, `vetor_bow.append(0)`.
  5. Imprima o vetor final.

---

## Etapa 5: Modularização e Escalonamento
Preparando o código para ler diversos arquivos (documentos) de uma vez, conforme exigido nas instruções.

* **O que entender:** Como automatizar a varredura de diretórios e organizar a lógica em módulos.
* **O que pesquisar:**
  * `How to read all text files in a directory in Python os.listdir() or glob`
  * `Python functions def and returning values`
* **Ação:** Refatore o código colocando as lógicas dentro de funções (`def`). Crie um fluxo principal que varre a pasta `entradas/`, limpa os textos, constrói um vocabulário global unificado e, em seguida, gera e salva o vetor BoW para cada arquivo individualmente.
