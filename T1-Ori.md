# TP1 - Processamento de arquivos, geração de vocabulário e bag of words

> **Prazo:** A entrega encerra hoje às 23:59.

---

## 1. Geração de Vocabulário
Fazer um programa em Python que receba como entrada um arquivo contendo um texto qualquer e devolva como saída um arquivo de texto contendo o vocabulário (termos de indexação) de tal arquivo.

### Pontos Importantes
* Os termos de indexação do arquivo de saída devem estar em ordem alfabética.
* Existe uma função no Python que faz a ordenação alfabética.
* Considere todas as palavras como com letras minúsculas ao processar o arquivo.
* Desconsidere pontuação e acentuação.
* Existem funções no Python que fazem essa remoção de pontuação e acentos.
* Faça testes com diferentes arquivos de entrada.

### Exemplo 1
**Entrada:**
> "Minha terra tem palmeiras,
> Onde canta o Sabiá;
> As aves, que aqui gorjeiam, Não gorjeiam como lá.
> Nosso céu tem mais estrelas,
> Nossas várzeas têm mais flores,
> Nossos bosques têm mais vida, Nossa vida mais amores."

**Saída:**
`amores, aqui, as, aves, bosques, canta, ceu, como, estrelas, flores, gorjeiam, la, mais, minha, nao, nossa, nossas, nosso, nossos, 0, onde, palmeiras, que, sabia, tem, terra, varzeas, vida`

---

## 2. Bag of Words
Fazer um programa (ou ajustes no seu programa anterior) que recebe como entrada o arquivo de vocabulário e um arquivo de texto representando um documento. O programa deve devolver como saída a representação "bag of words" (presença/ausência de termos) de tal arquivo texto.

### Exemplo 2
**Entrada 1 (Vocabulário):** Termos gerados na saída do Exemplo 1.

**Entrada 2 (Documento):**
> "Minha terra tem palmeiras,
> Onde canta o Sabiá;
> As aves, que aqui gorjeiam,
> Não gorjeiam como lá."

**Saída:**
`[0, 1, 1, 1, 0, 1, 0, 1, 0, 0, 1, 1, 0, 1, 1, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1, 1, 0, 0]`

---

## Detalhes de Implementação e Arquitetura
* Pense em como você poderia generalizar o seu programa lendo diversos arquivos (documentos) de uma vez.
* Dentro do possível, tente modularizar o seu código com o uso de funções.

## Entrega e Desenvolvimento
* Na sala de aula, use IDEs online como o Google Colab.
* Em casa, podem usar o Pycharm ou seguir com o próprio Colab (há inclusive extensão do Colab para o vscode).
* Cada grupo deve anexar como resposta o arquivo Jupyter Notebook (extensão `.ipynb`) correspondente aos itens 1 e 2.
* Separe os exercícios em diferentes células do notebook e anexe os arquivos de entrada correspondentes.
* Colocar na célula inicial do Notebook o nome completo dos integrantes do Grupo.
* Exigência de formação: 3 a 5 membros por grupo.

## Dicas Úteis
* Primeiro o arquivo deve ser aberto usando a função `open()` e depois lido usando a função `read()`.
* A função `unidecode` da biblioteca "Unidecode" ajuda no tratamento das palavras-chave.
* A função `split()` é muito importante.
* Aprender como percorrer um vetor em Python será essencial para separar as palavras repetidas e criar o vocabulário.