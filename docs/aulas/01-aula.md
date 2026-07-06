# 01. Conjuntos: fundamentos e operações

!!! info "Nesta aula"
    - O que é um conjunto e como descrevê-lo.
    - Pertinência, subconjunto, conjunto vazio e universo.
    - Operações: união, interseção, diferença e complemento.
    - Como tudo isso vira código em **Python**.

## 🧩 O que é um conjunto?

Um **conjunto** é uma coleção **não ordenada** de elementos **distintos**. Ele é
a peça de LEGO mais básica da matemática discreta: quase tudo — relações,
funções, grafos — é definido em cima de conjuntos.

Escrevemos conjuntos de duas formas:

=== "Por extensão"
    Listando os elementos:

    $$A = \{1, 2, 3, 4\}$$

=== "Por compreensão"
    Descrevendo uma **propriedade**:

    $$A = \{\, x \mid x \in \mathbb{N},\ 1 \le x \le 4 \,\}$$

    Lê-se: "o conjunto dos $x$ tais que $x$ é natural entre 1 e 4".

!!! note "Ordem e repetição não importam"
    $\{1, 2, 3\} = \{3, 1, 2\} = \{1, 1, 2, 3\}$. Um conjunto só registra
    **quais** elementos existem, não quantas vezes nem em que ordem.

## 🔑 Vocabulário essencial

| Símbolo | Significado | Exemplo |
| :--- | :--- | :--- |
| $\in$ | pertence a | $2 \in \{1,2,3\}$ |
| $\notin$ | não pertence a | $5 \notin \{1,2,3\}$ |
| $\subseteq$ | subconjunto de | $\{1,2\} \subseteq \{1,2,3\}$ |
| $\varnothing$ | conjunto vazio | $\{\,\}$ |
| $\mathcal{U}$ | conjunto universo | contexto do problema |
| $\lvert A \rvert$ | cardinalidade (nº de elementos) | $\lvert\{1,2,3\}\rvert = 3$ |
| $\subset$ | subconjunto **próprio** | $\{1,2\} \subset \{1,2,3\}$ |

!!! note "Subconjunto vs. subconjunto próprio"
    $A \subseteq B$ admite que $A$ seja **igual** a $B$. Já $A \subset B$ (próprio)
    exige que $B$ tenha **pelo menos um** elemento a mais. Todo conjunto é
    subconjunto de si mesmo ($A \subseteq A$) e o vazio é subconjunto de
    **qualquer** conjunto ($\varnothing \subseteq A$).

### Conjunto das partes (conjunto potência)

O **conjunto das partes** $\mathcal{P}(A)$ é o conjunto de **todos** os
subconjuntos de $A$ — incluindo $\varnothing$ e o próprio $A$. Se $A$ tem $n$
elementos, então $\mathcal{P}(A)$ tem $2^n$ elementos.

$$A = \{1, 2\} \ \Rightarrow\ \mathcal{P}(A) = \big\{\ \varnothing,\ \{1\},\ \{2\},\ \{1,2\}\ \big\}, \quad \lvert \mathcal{P}(A) \rvert = 2^2 = 4$$

## ⚙️ Operações com conjuntos

Considere $A = \{1,2,3,4\}$ e $B = \{3,4,5,6\}$, com universo $\mathcal{U} = \{1,\dots,9\}$.

=== "União ∪"
    Tudo que está em $A$ **ou** em $B$: $A \cup B = \{1,2,3,4,5,6\}$.

=== "Interseção ∩"
    O que está em $A$ **e** em $B$: $A \cap B = \{3,4\}$.

=== "Diferença −"
    O que está em $A$ **mas não** em $B$: $A - B = \{1,2\}$.

=== "Complemento"
    O que **não** está em $A$ (dentro de $\mathcal{U}$):
    $\overline{A} = \{5,6,7,8,9\}$.

=== "Diferença simétrica △"
    O que está em **exatamente um** dos dois (nunca nos dois):
    $A \,\triangle\, B = (A - B) \cup (B - A) = \{1,2,5,6\}$.

    Equivale a $(A \cup B) - (A \cap B)$.

!!! note "Cardinalidade da união (prévia da contagem)"
    Quando há sobreposição, somar $\lvert A\rvert$ e $\lvert B\rvert$ conta a
    interseção **duas vezes**. Por isso:
    $$\lvert A \cup B \rvert = \lvert A \rvert + \lvert B \rvert - \lvert A \cap B \rvert$$
    Essa é a versão para dois conjuntos do **princípio da inclusão-exclusão**,
    que retomaremos na [Aula 08](08-aula.md).

### Visualizando com diagramas de Venn

```mermaid
graph LR
    subgraph U["Universo 𝓤"]
        A(("A")) --- inter(("A ∩ B")) --- B(("B"))
    end
```

## 🐍 Conjuntos em Python

Python tem o tipo `set` nativo, e os operadores espelham a matemática:

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}
U = set(range(1, 10))  # {1, 2, ..., 9}

print(A | B)   # União        -> {1, 2, 3, 4, 5, 6}
print(A & B)   # Interseção   -> {3, 4}
print(A - B)   # Diferença    -> {1, 2}
print(U - A)   # Complemento  -> {5, 6, 7, 8, 9}

print(A ^ B)   # Dif. simétrica -> {1, 2, 5, 6}

print(2 in A)          # Pertinência -> True
print({1, 2} <= A)     # Subconjunto  -> True
print({1, 2} < A)      # Subconjunto próprio -> True
print(len(A))          # Cardinalidade -> 4
```

!!! warning "`<=` é subconjunto, não é ordem numérica"
    Entre conjuntos, `<=` significa "está contido em" ($\subseteq$) e `<`
    significa "está contido propriamente em" ($\subset$). Não confunda com a
    comparação de números.

!!! tip "Conjunto por compreensão em Python"
    A notação por compreensão da matemática tem par direto no código:

    ```python
    pares = {x for x in range(1, 11) if x % 2 == 0}
    print(pares)  # {2, 4, 6, 8, 10}
    ```

## 📐 Leis úteis

As operações de conjuntos seguem leis parecidas com as da aritmética. As mais
usadas:

| Lei | Forma |
| :--- | :--- |
| Comutativa | $A \cup B = B \cup A$; $\quad A \cap B = B \cap A$ |
| Associativa | $(A \cup B) \cup C = A \cup (B \cup C)$ |
| Distributiva | $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$ |
| Identidade | $A \cup \varnothing = A$; $\quad A \cap \mathcal{U} = A$ |
| **De Morgan** | $\overline{A \cup B} = \overline{A} \cap \overline{B}$ |
| **De Morgan** | $\overline{A \cap B} = \overline{A} \cup \overline{B}$ |

As **Leis de De Morgan** (que reveremos na [lógica](05-aula.md)) dizem que
negar uma união vira interseção dos complementos, e vice-versa.

!!! example "De Morgan passo a passo"
    Com $\mathcal{U} = \{1,\dots,10\}$, $A=\{1,2,3,4\}$ e $B=\{3,4,5,6\}$:

    - $A \cup B = \{1,2,3,4,5,6\}$, logo $\overline{A \cup B} = \{7,8,9,10\}$.
    - $\overline{A} = \{5,6,7,8,9,10\}$ e $\overline{B} = \{1,2,7,8,9,10\}$.
    - $\overline{A} \cap \overline{B} = \{7,8,9,10\}$. ✅ Coincide.

## 📝 Exercícios

??? abstract "Exercício 1 — Aquecimento"
    Dados $A = \{1,2,3,4,5\}$ e $B = \{2,4,6,8\}$, calcule à mão e depois
    confira em Python: $A \cup B$, $A \cap B$, $A - B$ e $B - A$.

??? abstract "Exercício 2 — Compreensão"
    Escreva por compreensão (em matemática **e** em Python) o conjunto dos
    múltiplos de 3 entre 1 e 30.

??? abstract "Exercício 3 — De Morgan na prática"
    Com $\mathcal{U} = \{1,\dots,10\}$, $A=\{1,2,3,4\}$ e $B=\{3,4,5,6\}$,
    verifique em Python que $\overline{A \cup B} = \overline{A} \cap \overline{B}$.

??? abstract "Exercício 4 — Desafio"
    Escreva uma função `simetrica(A, B)` que devolva a **diferença simétrica**
    (elementos que estão em exatamente um dos conjuntos) **sem** usar o operador
    `^`. Compare seu resultado com `A ^ B`.

    *Dica:* $A \,\triangle\, B = (A - B) \cup (B - A)$.

## 📚 Referências

**Livros (teoria)**

- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. Porto Alegre:
  AMGH/McGraw-Hill — cap. **Teoria dos Conjuntos**.
- GERSTING, J. L. *Fundamentos Matemáticos para a Ciência da Computação*. 7. ed.
  Rio de Janeiro: LTC — cap. **Conjuntos e Combinatória**.
- SCHEINERMAN, E. R. *Matemática Discreta: uma introdução*. São Paulo: Cengage —
  seção sobre **conjuntos e operações**.
- LIPSCHUTZ, S.; LIPSON, M. *Matemática Discreta* (Coleção Schaum). Porto Alegre:
  Bookman — cap. **Teoria dos Conjuntos** (muitos exercícios resolvidos).

**Documentação e prática (Python)**

- Python — *Sets* (tutorial oficial): <https://docs.python.org/3/tutorial/datastructures.html#sets>
- Python — tipo `set` / `frozenset`: <https://docs.python.org/3/library/stdtypes.html#set-types-set-frozenset>

!!! tip "Próxima Parada 🚏"
    Hora de praticar! Resolva a **[Lista 01 — Conjuntos](../listas/01-lista.md)**
    e entregue no Google Classroom. Na próxima aula veremos **[Relações](02-aula.md)**,
    que nascem justamente de conjuntos.
