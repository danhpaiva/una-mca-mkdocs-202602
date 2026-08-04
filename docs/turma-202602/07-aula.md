# 07. Álgebra Booleana e suas aplicações — Parte 2

!!! info "Nesta aula"
    - Forma normal soma de produtos (SOP).
    - Mapas de Karnaugh para simplificar visualmente.
    - Aplicações práticas da simplificação.

## 🧮 Da tabela-verdade à expressão (SOP)

Um **mintermo** é um produto (AND) que vale $1$ em **exatamente uma** linha da
tabela-verdade, usando a variável direta quando ela é $1$ e complementada
quando é $0$. A **soma de produtos** (SOP) é a soma (OR) dos mintermos das
linhas em que $f = 1$.

Exemplo — o XOR:

| $x$ | $y$ | $f(x,y)$ |
| :-: | :-: | :-: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

$f = 1$ em $(0,1)$ e $(1,0)$, então:

$$f(x,y) = \overline{x}\,y + x\,\overline{y}$$

## 🗺️ Mapas de Karnaugh

Um **mapa de Karnaugh** (K-map) é uma reorganização visual da tabela-verdade
em que células **adjacentes** diferem em **apenas uma variável** — isso
permite "ver" simplificações que, na álgebra pura, exigiriam vários passos.

### K-map de 2 variáveis

Para $f(x,y) = \overline{x}\,y + x\,\overline{y} + x\,y$ (equivale a $x + y$):

|       | $y=0$ | $y=1$ |
| :---: | :---: | :---: |
| $x=0$ | 0     | 1     |
| $x=1$ | 1     | 1     |

Agrupamos os $1$s adjacentes em blocos de tamanho potência de 2 (1, 2, 4...).
Aqui há dois grupos possíveis de tamanho 2: a linha $x=1$ inteira (sobra
apenas $x$) e a coluna $y=1$ inteira (sobra apenas $y$) — cobrindo os três
$1$s com $x + y$.

### K-map de 3 variáveis

Para simplificar $f(x,y,z) = \overline{x}\,\overline{y}\,z +
\overline{x}\,y\,z + x\,\overline{y}\,z + x\,y\,z$, montamos o mapa com as
colunas em **código Gray** ($00, 01, 11, 10$) — assim colunas vizinhas também
diferem em só uma variável:

|       | $yz=00$ | $yz=01$ | $yz=11$ | $yz=10$ |
| :---: | :-----: | :-----: | :-----: | :-----: |
| $x=0$ | 0       | 1       | 1       | 0       |
| $x=1$ | 0       | 1       | 1       | 0       |

!!! warning "Por que código Gray, e não binário puro?"
    Em ordem binária normal ($00, 01, 10, 11$), as colunas $01$ e $10$ **não**
    são adjacentes na tabela mas parecem estar lado a lado — o que quebraria
    a regra de "vizinhos diferem em 1 variável". O código Gray garante que
    colunas fisicamente vizinhas realmente diferem em apenas um bit.

Todos os $1$s estão nas duas colunas centrais ($yz=01$ e $yz=11$), formando um
retângulo $2\times2$. Nesse grupo, $x$ varia (0 e 1) e $z$ é sempre 1 — então
$x$ "sai" da expressão e sobra:

$$f(x,y,z) = z$$

Bem mais simples que a soma de 4 mintermos original!

!!! tip "Regra prática de agrupamento"
    1. Agrupe $1$s adjacentes em blocos de $1, 2, 4, 8, \dots$ células.
    2. Prefira os **maiores** blocos possíveis (menos literais na expressão).
    3. Uma variável **desaparece** do grupo se ela muda de valor dentro dele;
       as que **não mudam** formam o produto final daquele grupo.
    4. Some (OR) os produtos de todos os grupos necessários para cobrir todos
       os $1$s.

!!! warning "As bordas do mapa 'se tocam' (adjacência circular)"
    Um K-map é topologicamente um **cilindro** (ou torus, com 4+ variáveis):
    a última coluna é vizinha da **primeira**, e a última linha é vizinha da
    **primeira**. No K-map de 3 variáveis acima, a coluna $yz=10$ (a última)
    é adjacente à coluna $yz=00$ (a primeira) — elas diferem só em $y$. Não
    esqueça de testar esses agrupamentos "que dão a volta".

!!! example "Quando não importa o valor: condições 'don't care'"
    Às vezes uma combinação de entrada **nunca acontece** na prática (ex.:
    um sensor que não pode fisicamente registrar certos valores). Marcamos
    essas células do K-map com **X** (don't care) e escolhemos livremente
    se elas "valem" 0 ou 1 — o que ajuda a formar grupos maiores e uma
    expressão ainda mais simples. Um X só é usado a favor da simplificação;
    nunca é necessário cobri-lo.

## 🌍 Por que isso importa na prática

- Cada literal a menos numa expressão simplificada é (em geral) **uma porta
  lógica a menos** no circuito final — menor custo, menor consumo, menor
  chance de falha.
- Ferramentas de projeto de chips fazem esse tipo de simplificação
  automaticamente, em escala de milhões de variáveis — o K-map é a versão
  "à mão" do mesmo princípio.
- Veremos isso virar fios e portas de verdade na
  **[próxima aula de conteúdo](10-aula.md)**.

## 📝 Exercícios

??? abstract "Exercício 1 — SOP"
    Escreva a soma de produtos de $f(x,y) = 1$ apenas quando $x=1$ e $y=0$, ou
    quando $x=0$ e $y=1$. Que operação lógica conhecida é essa?

??? abstract "Exercício 2 — K-map de 2 variáveis"
    Monte o K-map de $f(x,y) = xy + \overline{x}\,\overline{y}$ e simplifique
    visualmente, se possível.

??? abstract "Exercício 3 — K-map de 3 variáveis"
    Monte o K-map de $f(x,y,z)$ que vale 1 nas linhas
    $(0,0,1), (0,1,1), (1,0,1), (1,1,1)$ e 0 nas demais. Encontre a expressão
    simplificada (compare com o exemplo da aula).

??? abstract "Exercício 4 — Desafio"
    Pegue a expressão original do XOR ($\overline{x}\,y + x\,\overline{y}$) e
    tente simplificá-la com um K-map de 2 variáveis. O que acontece? Por que o
    XOR é "resistente" à simplificação por agrupamento?

## 📚 Referências

**Livros (teoria)**

- IDOETA, I. V.; CAPUANO, F. G. *Elementos de Eletrônica Digital*. Érica —
  cap. **Mapas de Karnaugh**.
- TOCCI, R. J.; WIDMER, N. S.; MOSS, G. L. *Sistemas Digitais: princípios e
  aplicações*. Pearson — **simplificação por mapa de Karnaugh**.
- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. AMGH/McGraw-Hill
  — cap. **Álgebra Booleana** (formas normais e simplificação).

**Documentação e prática (Python)**

- SymPy — simplificação simbólica de expressões booleanas:
  <https://docs.sympy.org/latest/modules/logic.html>

!!! tip "Conferindo uma simplificação com SymPy"
    ```python
    from sympy import symbols
    from sympy.logic import SOPform, simplify_logic

    x, y, z = symbols("x y z")
    # mintermos onde f(x,y,z) = 1, na ordem (x,y,z)
    expressao = SOPform([x, y, z], [[0,1,0], [0,1,1], [1,0,1], [1,1,1]])
    print(simplify_logic(expressao))  # confere se bate com o K-map feito à mão
    ```

**🎥 Vídeos**

- Mapas de Karnaugh explicados com exemplos de 2, 3 e 4 variáveis:
  <https://www.youtube.com/results?search_query=mapa+de+karnaugh+2+3+4+vari%C3%A1veis+exemplos>
- Condições "don't care" em mapas de Karnaugh:
  <https://www.youtube.com/results?search_query=dont+care+karnaugh+map+simplification>

!!! tip "Próxima Parada 🚏"
    Vamos consolidar tudo numa
    **[aula de atividades e prática](08-aula.md)**.
