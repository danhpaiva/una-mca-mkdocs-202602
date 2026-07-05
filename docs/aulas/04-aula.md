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

## 🏛️ Classificando fórmulas

- **Tautologia**: verdadeira em **todas** as linhas. Ex.: $p \vee \neg p$.
- **Contradição**: falsa em todas. Ex.: $p \wedge \neg p$.
- **Contingência**: depende dos valores.

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

!!! tip "Próxima Parada 🚏"
    Vá para a **[Lista 04 — Lógica proposicional](../listas/04-lista.md)**. Na
    próxima aula usaremos essas tabelas para provar
    **[equivalências e validar argumentos](05-aula.md)**.
