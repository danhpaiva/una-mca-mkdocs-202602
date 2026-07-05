# 05. Equivalências lógicas e argumentos

!!! info "Nesta aula"
    - Equivalência lógica ($\equiv$).
    - As principais leis (De Morgan, distributiva, etc.).
    - Argumentos válidos e regras de inferência.
    - Como testar validade com tabelas-verdade.

## 🟰 Equivalência lógica

Duas fórmulas são **logicamente equivalentes** ($P \equiv Q$) quando têm a
**mesma tabela-verdade** — ou seja, $P \leftrightarrow Q$ é uma tautologia.

**Exemplo clássico:** a condicional em termos de ∨:

$$p \to q \equiv \neg p \vee q$$

| $p$ | $q$ | $p \to q$ | $\neg p \vee q$ |
| :-: | :-: | :-: | :-: |
| V | V | V | V |
| V | F | F | F |
| F | V | V | V |
| F | F | V | V |

As colunas coincidem → são equivalentes. ✅

## 📚 Leis fundamentais

| Lei | Forma |
| :--- | :--- |
| Identidade | $p \wedge V \equiv p$; $\quad p \vee F \equiv p$ |
| Dominação | $p \vee V \equiv V$; $\quad p \wedge F \equiv F$ |
| Dupla negação | $\neg(\neg p) \equiv p$ |
| **De Morgan** | $\neg(p \wedge q) \equiv \neg p \vee \neg q$ |
| **De Morgan** | $\neg(p \vee q) \equiv \neg p \wedge \neg q$ |
| Distributiva | $p \wedge (q \vee r) \equiv (p \wedge q) \vee (p \wedge r)$ |
| Contrapositiva | $p \to q \equiv \neg q \to \neg p$ |

!!! tip "De Morgan em uma frase"
    Negar um "E" vira "OU" (e vice-versa), **trocando** cada parte pela sua
    negação. "Não é verdade que choveu **e** ventou" = "não choveu **ou** não ventou".

## 🧠 Argumentos e validade

Um **argumento** tem **premissas** e uma **conclusão**. Ele é **válido** quando,
sempre que **todas** as premissas são verdadeiras, a conclusão **também** é.

$$\frac{p \to q,\quad p}{\therefore\ q} \quad\text{(Modus Ponens)}$$

### Regras de inferência úteis

=== "Modus Ponens"
    De $p \to q$ e $p$, conclua $q$.

=== "Modus Tollens"
    De $p \to q$ e $\neg q$, conclua $\neg p$.

=== "Silogismo Hipotético"
    De $p \to q$ e $q \to r$, conclua $p \to r$.

!!! danger "Falácias comuns"
    - **Afirmação do consequente:** de $p \to q$ e $q$ **não** se conclui $p$.
    - **Negação do antecedente:** de $p \to q$ e $\neg p$ **não** se conclui $\neg q$.

## 🔎 Testando validade com tabela-verdade

Um argumento é válido sse a fórmula
$(\text{premissas}) \to (\text{conclusão})$ for **tautologia**.

## 🐍 Validando argumentos em Python

```python
from itertools import product

def modus_ponens_valido():
    # Premissas: p->q, p   Conclusão: q
    for p, q in product([True, False], repeat=2):
        premissas = ((not p or q) and p)   # (p->q) e p
        if premissas and not q:            # premissas V, conclusão F?
            return False                   # achou contraexemplo
    return True

print(modus_ponens_valido())  # True -> argumento válido
```

!!! note "Estratégia"
    Se o laço **nunca** encontra uma linha com premissas V e conclusão F, o
    argumento é válido. Uma única linha assim já o invalida.

## 📝 Exercícios

??? abstract "Exercício 1"
    Prove por tabela-verdade que $\neg(p \vee q) \equiv \neg p \wedge \neg q$.

??? abstract "Exercício 2"
    Reescreva "Se não estudo, então não passo" usando a **contrapositiva**.

??? abstract "Exercício 3"
    O argumento a seguir é válido? Premissas: $p \to q$, $\neg p$. Conclusão:
    $\neg q$. Justifique com tabela-verdade.

??? abstract "Exercício 4 — Desafio"
    Generalize o código da aula em `eh_valido(premissas, conclusao, n_vars)`,
    onde `premissas` é uma lista de `lambda`s. Teste com Modus Tollens.

!!! tip "Próxima Parada 🚏"
    Resolva a **[Lista 05 — Equivalências e argumentos](../listas/05-lista.md)**.
    A seguir levamos a lógica para o hardware com a
    **[Álgebra booleana](06-aula.md)**.
