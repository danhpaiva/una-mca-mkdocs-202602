# 02. Relações

!!! info "Nesta aula"
    - Produto cartesiano como base das relações.
    - O que é uma relação binária.
    - Propriedades: reflexiva, simétrica, transitiva.
    - Relações de equivalência e de ordem.

## ✖️ Produto cartesiano

Antes de "relacionar" elementos, precisamos de **pares ordenados**. O
**produto cartesiano** $A \times B$ é o conjunto de todos os pares $(a, b)$ com
$a \in A$ e $b \in B$:

$$A \times B = \{\, (a,b) \mid a \in A,\ b \in B \,\}$$

Se $A = \{1,2\}$ e $B = \{x, y\}$:

$$A \times B = \{(1,x), (1,y), (2,x), (2,y)\}$$

!!! note "Aqui a ordem importa!"
    Diferente de conjuntos, em pares **ordenados** $(1, x) \neq (x, 1)$. E
    $\lvert A \times B \rvert = \lvert A \rvert \cdot \lvert B \rvert$.

## 🔗 O que é uma relação

Uma **relação binária** $R$ de $A$ em $B$ é simplesmente **um subconjunto** de
$A \times B$. Escrevemos $a\,R\,b$ quando $(a,b) \in R$.

**Exemplo:** em $A = \{1,2,3,4\}$, a relação "divide" ($a \mid b$):

$$R = \{(1,1),(1,2),(1,3),(1,4),(2,2),(2,4),(3,3),(4,4)\}$$

```mermaid
graph LR
    1 --> 1 & 2 & 3 & 4
    2 --> 2b[2] & 4b[4]
    3 --> 3b[3]
    4 --> 4c[4]
```

## 🧭 Propriedades de relações em um conjunto

Quando $R \subseteq A \times A$ (relação **em** $A$), analisamos três propriedades-chave:

=== "Reflexiva"
    Todo elemento se relaciona consigo mesmo:
    $$\forall a \in A,\ (a,a) \in R$$
    Ex.: "é igual a", "divide".

=== "Simétrica"
    Se $a$ se relaciona com $b$, então $b$ com $a$:
    $$\forall a,b,\ (a,b) \in R \Rightarrow (b,a) \in R$$
    Ex.: "é irmão de", "tem a mesma idade que".

=== "Transitiva"
    Encadeamento:
    $$(a,b) \in R \wedge (b,c) \in R \Rightarrow (a,c) \in R$$
    Ex.: "é menor que", "é ancestral de".

## 🏷️ Dois tipos especiais

| Tipo | Reflexiva | Simétrica | Antissimétrica | Transitiva |
| :--- | :---: | :---: | :---: | :---: |
| **Equivalência** | ✅ | ✅ | — | ✅ |
| **Ordem parcial** | ✅ | — | ✅ | ✅ |

- **Relação de equivalência** particiona o conjunto em *classes* (ex.: "mesmo
  resto na divisão por 3").
- **Relação de ordem** organiza os elementos (ex.: $\le$, "divide").

## 🐍 Relações em Python

Representamos uma relação como um **conjunto de tuplas** e testamos suas propriedades:

```python
def reflexiva(R, A):
    return all((a, a) in R for a in A)

def simetrica(R):
    return all((b, a) in R for (a, b) in R)

def transitiva(R):
    return all((a, c) in R
               for (a, b) in R
               for (x, c) in R if b == x)

A = {1, 2, 3}
R = {(1, 1), (2, 2), (3, 3), (1, 2), (2, 1)}

print(reflexiva(R, A))   # True
print(simetrica(R))      # True
print(transitiva(R))     # True  -> é relação de equivalência
```

!!! tip "Produto cartesiano em Python"
    ```python
    from itertools import product
    A, B = {1, 2}, {"x", "y"}
    print(set(product(A, B)))
    # {(1, 'x'), (1, 'y'), (2, 'x'), (2, 'y')}
    ```

## 📝 Exercícios

??? abstract "Exercício 1"
    Liste $A \times B$ para $A = \{a,b,c\}$ e $B = \{0,1\}$. Quantos pares há?

??? abstract "Exercício 2"
    A relação "$a$ e $b$ têm o mesmo resto na divisão por 3" sobre
    $\{0,1,\dots,8\}$ é de equivalência? Liste suas classes.

??? abstract "Exercício 3"
    Classifique a relação $\le$ sobre $\{1,2,3,4\}$: quais das três propriedades
    ela satisfaz? É ordem ou equivalência?

??? abstract "Exercício 4 — Desafio"
    Implemente `eh_equivalencia(R, A)` reutilizando as funções da aula e teste
    com pelo menos um exemplo verdadeiro e um falso.

!!! tip "Próxima Parada 🚏"
    Pratique na **[Lista 02 — Relações](../listas/02-lista.md)**. Em seguida,
    veremos um tipo *muito* especial de relação: as **[Funções](03-aula.md)**.
