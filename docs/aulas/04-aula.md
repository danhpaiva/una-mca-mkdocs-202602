# 04. Lógica proposicional e tabelas-verdade

!!! info "Nesta aula"
    - O que é uma proposição.
    - Conectivos: ¬, ∧, ∨, →, ↔.
    - Construção de tabelas-verdade.
    - Tautologia, contradição e contingência.

## 💬 Proposições

Uma **proposição** é uma afirmação que é **verdadeira (V)** ou **falsa (F)** —
nunca as duas coisas.

- ✅ "7 é primo." (proposição, V)
- ✅ "3 > 10." (proposição, F)
- ❌ "Que horas são?" (não é proposição)

Representamos proposições por letras: $p, q, r, \dots$

## 🔌 Conectivos lógicos

| Conectivo | Símbolo | Nome | Lê-se |
| :--- | :---: | :--- | :--- |
| Negação | $\neg p$ | NOT | "não $p$" |
| Conjunção | $p \wedge q$ | AND | "$p$ e $q$" |
| Disjunção | $p \vee q$ | OR | "$p$ ou $q$" |
| Condicional | $p \to q$ | implica | "se $p$ então $q$" |
| Bicondicional | $p \leftrightarrow q$ | sse | "$p$ se e somente se $q$" |

### Precedência dos conectivos

Como na aritmética ($\times$ antes de $+$), os conectivos têm uma ordem. Do que
"amarra mais forte" para o mais fraco:

$$\neg \ \succ\ \wedge \ \succ\ \vee \ \succ\ \to \ \succ\ \leftrightarrow$$

Assim, $\neg p \vee q \wedge r$ lê-se $(\neg p) \vee (q \wedge r)$. Na dúvida,
**use parênteses** — eles nunca atrapalham.

### Traduzindo do português para a lógica

O passo mais importante é isolar as **proposições atômicas** (as afirmações que
não dá para quebrar) e dar uma letra a cada uma.

!!! example "Tradução"
    *"Se estudo **e** durmo bem, então passo na prova."*

    - $p$: "estudo"; $q$: "durmo bem"; $r$: "passo na prova".
    - Fórmula: $(p \wedge q) \to r$.

    Palavras como "e" → $\wedge$, "ou" → $\vee$, "não/nunca" → $\neg$,
    "se… então" → $\to$, "se e somente se" → $\leftrightarrow$.

## 📊 Tabelas-verdade

Uma tabela-verdade lista **todas** as combinações de valores das proposições.
Com $n$ variáveis há $2^n$ linhas.

=== "¬, ∧, ∨"
    | $p$ | $q$ | $\neg p$ | $p \wedge q$ | $p \vee q$ |
    | :-: | :-: | :-: | :-: | :-: |
    | V | V | F | V | V |
    | V | F | F | F | V |
    | F | V | V | F | V |
    | F | F | V | F | F |

=== "→, ↔"
    | $p$ | $q$ | $p \to q$ | $p \leftrightarrow q$ |
    | :-: | :-: | :-: | :-: |
    | V | V | V | V |
    | V | F | F | F |
    | F | V | V | F |
    | F | F | V | V |

!!! warning "A condicional confunde!"
    $p \to q$ só é **falsa** quando $p$ é V e $q$ é F. "Se chover, levo guarda-chuva"
    só é mentira se choveu **e** você **não** levou. Se não choveu, a promessa
    continua válida (verdadeira por vacuidade).

### Construindo uma tabela passo a passo

Para uma fórmula composta, crie **colunas intermediárias** e vá combinando.
Exemplo com $\neg(p \wedge q)$:

| $p$ | $q$ | $p \wedge q$ | $\neg(p \wedge q)$ |
| :-: | :-: | :-: | :-: |
| V | V | V | F |
| V | F | F | V |
| F | V | F | V |
| F | F | F | V |

Primeiro preenchemos $p \wedge q$; depois negamos essa coluna. Repare que o
resultado é igual a $\neg p \vee \neg q$ — uma **Lei de De Morgan**, que veremos
formalmente na [Aula 05](05-aula.md).

## 🏛️ Classificando fórmulas

- **Tautologia**: verdadeira em **todas** as linhas. Ex.: $p \vee \neg p$.
- **Contradição**: falsa em todas. Ex.: $p \wedge \neg p$.
- **Contingência**: depende dos valores (às vezes V, às vezes F).

!!! example "Classificando na prática"
    - $p \to (p \vee q)$: seja $p$ V ou F, o resultado é sempre V → **tautologia**.
    - $p \wedge \neg p$: nunca pode ser V (p e não-p ao mesmo tempo) → **contradição**.
    - $(p \to q) \vee p$: depende — é F, por exemplo, quando... nunca? Monte a
      tabela e descubra se é tautologia ou contingência. 😉

## 🐍 Lógica em Python

Os operadores `not`, `and`, `or` mapeiam direto. A condicional vira `not p or q`:

```python
def implica(p, q):
    return (not p) or q

def bicondicional(p, q):
    return p == q

# Gerando uma tabela-verdade de p -> q
print("p     q     p->q")
for p in (True, False):
    for q in (True, False):
        print(f"{p!s:<5} {q!s:<5} {implica(p, q)}")
```

!!! tip "Detectando tautologias automaticamente"
    ```python
    from itertools import product

    def eh_tautologia(func, n_vars):
        return all(func(*vals) for vals in product([True, False], repeat=n_vars))

    print(eh_tautologia(lambda p: p or not p, 1))          # True
    print(eh_tautologia(lambda p, q: implica(p, q), 2))    # False
    ```

## 📝 Exercícios

??? abstract "Exercício 1"
    Construa a tabela-verdade completa de $\neg(p \wedge q)$.

??? abstract "Exercício 2"
    Traduza para lógica: "Se estudo e durmo bem, então passo na prova." Identifique
    as proposições atômicas.

??? abstract "Exercício 3"
    Classifique como tautologia, contradição ou contingência:
    (a) $(p \to q) \vee p$; (b) $p \wedge \neg p$; (c) $p \to (p \vee q)$.

??? abstract "Exercício 4 — Desafio"
    Escreva uma função que **imprima** a tabela-verdade de qualquer fórmula com 3
    variáveis passada como `lambda`. Use `itertools.product`.

## 📚 Referências

**Livros (teoria)**

- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. AMGH/McGraw-Hill —
  cap. **Fundamentos: Lógica e Demonstrações** (proposições, conectivos, tabelas).
- GERSTING, J. L. *Fundamentos Matemáticos para a Ciência da Computação*. 7. ed.
  LTC — cap. **Lógica Formal**.
- MENEZES, P. B. *Matemática Discreta para Computação e Informática*. Bookman —
  cap. **Lógica Proposicional**.
- HUTH, M.; RYAN, M. *Logic in Computer Science*. Cambridge — introdução à
  **lógica proposicional** (referência avançada, em inglês).

**Documentação e prática (Python)**

- Python — operadores booleanos `and`, `or`, `not`: <https://docs.python.org/3/reference/expressions.html#boolean-operations>
- Python — `itertools.product` (gerar combinações V/F): <https://docs.python.org/3/library/itertools.html#itertools.product>

!!! tip "Próxima Parada 🚏"
    Vá para a **[Lista 04 — Lógica proposicional](../listas/04-lista.md)**. Na
    próxima aula usaremos essas tabelas para provar
    **[equivalências e validar argumentos](05-aula.md)**.
