# 04. Proposições lógicas e tabela-verdade dos conectivos

!!! info "Nesta aula"
    - Os cinco conectivos: negação, e, ou, se...então, se e somente se.
    - Tabela-verdade de cada um.
    - Precedência entre conectivos.
    - Como isso vira código em Python.

## 🔧 Os cinco conectivos

Cada conectivo combina o valor lógico de uma ou duas proposições para produzir
um novo valor lógico.

=== "Negação ¬"
    Inverte o valor: "não $p$".

    | $p$ | $\neg p$ |
    | :-: | :-: |
    | V | F |
    | F | V |

=== "Conjunção ∧ (e)"
    "$p$ **e** $q$" — verdadeira só quando **ambas** são verdadeiras.

    | $p$ | $q$ | $p \wedge q$ |
    | :-: | :-: | :-: |
    | V | V | V |
    | V | F | F |
    | F | V | F |
    | F | F | F |

=== "Disjunção ∨ (ou)"
    "$p$ **ou** $q$" — verdadeira quando **pelo menos uma** é verdadeira.

    | $p$ | $q$ | $p \vee q$ |
    | :-: | :-: | :-: |
    | V | V | V |
    | V | F | V |
    | F | V | V |
    | F | F | F |

=== "Condicional → (se...então)"
    "**se** $p$ **então** $q$" — só é **falsa** quando $p$ é V e $q$ é F.

    | $p$ | $q$ | $p \to q$ |
    | :-: | :-: | :-: |
    | V | V | V |
    | V | F | F |
    | F | V | V |
    | F | F | V |

=== "Bicondicional ↔ (se e somente se)"
    "$p$ **se e somente se** $q$" — verdadeira quando $p$ e $q$ têm o
    **mesmo** valor.

    | $p$ | $q$ | $p \leftrightarrow q$ |
    | :-: | :-: | :-: |
    | V | V | V |
    | V | F | F |
    | F | V | F |
    | F | F | V |

!!! warning "O condicional é o mais contraintuitivo"
    "Se $p$ então $q$" ($p \to q$) só é **falsa** quando $p$ é verdadeira e a
    promessa não se cumpre ($q$ falsa). Se $p$ já é falsa, o condicional é
    **sempre verdadeiro** — "se eu fosse rico eu compraria um avião" não é uma
    mentira só porque eu não sou rico. Chamamos isso de **vacuosamente
    verdadeiro**.

!!! example "Lendo o condicional em contexto"
    "Se chove ($p$), então a rua fica molhada ($q$)."

    - Chove e a rua molha → $p\to q$ é **V** (a promessa se cumpriu).
    - Chove e a rua **não** molha → $p\to q$ é **F** (a promessa foi quebrada).
    - Não chove, rua molha (ex.: alguém lavou a calçada) → $p\to q$ ainda é
      **V**: a implicação só fala do que acontece **quando chove**.
    - Não chove e rua não molha → $p\to q$ é **V**, vacuamente.

## 🗣️ Reconhecendo conectivos em português

Nem sempre a palavra do conectivo aparece de forma óbvia. Fique atento a
estas variações comuns:

| Conectivo | Formas comuns em português |
| :--- | :--- |
| $\wedge$ (e) | "e", "mas", "porém", "apesar de", vírgula entre duas afirmações |
| $\vee$ (ou) | "ou", "ou então" |
| $\to$ (se...então) | "se... então", "quando", "desde que", "só se acontece X, então Y" |
| $\leftrightarrow$ (se e somente se) | "se e somente se", "é equivalente a", "exatamente quando" |
| $\neg$ (não) | "não", "nunca", prefixos como "in-", "im-", "des-" |

!!! example "Traduzindo frases reais"
    - "Estou cansado, **mas** vou estudar." → $p \wedge q$ (o "mas" aqui
      funciona como "e").
    - "**Desde que** você tenha o crachá, pode entrar." → crachá $\to$ entrada.
    - "Você aprova **exatamente quando** tira nota ≥ 6." →
      aprovado $\leftrightarrow$ (nota ≥ 6).

!!! example "Bicondicional no dia a dia"
    "Está frio se e somente se a temperatura está abaixo de 15°C."

    | Está frio ($p$) | Temp. < 15°C ($q$) | $p \leftrightarrow q$ | Interpretação |
    | :-: | :-: | :-: | :--- |
    | V | V | V | Consistente: está frio e a temperatura confirma |
    | V | F | F | Contradição: "está frio" mas a temperatura diz que não |
    | F | V | F | Contradição: a temperatura diz frio, mas você diz que não está |
    | F | F | V | Consistente: nem está frio, nem a temperatura indica frio |

## 🎯 Precedência dos conectivos

Assim como $\times$ tem prioridade sobre $+$ na aritmética, os conectivos têm
uma ordem de avaliação (da maior para a menor prioridade):

$$\neg \quad > \quad \wedge \quad > \quad \vee \quad > \quad \to \quad > \quad \leftrightarrow$$

$$\neg p \vee q \wedge r \quad \text{significa} \quad (\neg p) \vee (q \wedge r)$$

!!! tip "Na dúvida, use parênteses"
    Precedência existe para desambiguar, mas **parênteses explícitos** deixam
    a fórmula legível para qualquer leitor — inclusive você mesmo, duas
    semanas depois.

## 🐍 Conectivos em Python

| Conectivo | Python |
| :--- | :--- |
| $\neg p$ | `not p` |
| $p \wedge q$ | `p and q` |
| $p \vee q$ | `p or q` |
| $p \to q$ | `(not p) or q` |
| $p \leftrightarrow q$ | `p == q` |

```python
def implica(p, q):
    return (not p) or q

def bicondicional(p, q):
    return p == q

for p in (True, False):
    for q in (True, False):
        print(p, q, "->", implica(p, q), "<->", bicondicional(p, q))
```

!!! note "Python não tem operador nativo para → e ↔"
    Diferente de `and`/`or`/`not`, o condicional e o bicondicional não têm
    símbolo próprio em Python — nós os **construímos** a partir dos
    operadores existentes, como fizemos acima.

## 📝 Exercícios

??? abstract "Exercício 1 — Tabela-verdade"
    Monte a tabela-verdade completa de $\neg p \vee q$. Compare com a tabela
    de $p \to q$. O que você percebe?

??? abstract "Exercício 2 — Precedência"
    Sem usar parênteses adicionais, avalie $p \vee q \wedge \neg r$ para
    $p{=}F$, $q{=}V$, $r{=}V$. Depois reescreva a fórmula usando parênteses
    para deixar a ordem explícita.

??? abstract "Exercício 3 — Traduzindo"
    Traduza para lógica formal: "Se estudo e durmo bem, então passo na prova."
    Identifique $p$, $q$, $r$ e o(s) conectivo(s) usado(s).

??? abstract "Exercício 4 — Desafio"
    Implemente `bicondicional_v2(p, q)` usando **apenas** `and`, `or` e `not`
    (sem usar `==`). Teste contra `bicondicional` da aula para as 4
    combinações de `p` e `q`.

## 📚 Referências

**Livros (teoria)**

- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. AMGH/McGraw-Hill
  — cap. **Lógica Proposicional** (conectivos e tabelas-verdade).
- GERSTING, J. L. *Fundamentos Matemáticos para a Ciência da Computação*.
  7. ed. LTC — cap. **Lógica**.
- LIPSCHUTZ, S.; LIPSON, M. *Matemática Discreta* (Coleção Schaum). Bookman —
  cap. **Lógica Proposicional**.

**Documentação e prática (Python)**

- Python — operações booleanas: <https://docs.python.org/3/reference/expressions.html#boolean-operations>
- Python — operadores de comparação (`==`): <https://docs.python.org/3/library/stdtypes.html#comparisons>

**🎥 Vídeos**

- Conectivos lógicos e tabelas-verdade explicados passo a passo:
  <https://www.youtube.com/results?search_query=conectivos+l%C3%B3gicos+tabela+verdade+explica%C3%A7%C3%A3o>
- Canal **Prof. Ferretto** — aulas de lógica matemática e raciocínio lógico
  com muitos exercícios resolvidos:
  <https://www.youtube.com/results?search_query=prof+ferretto+l%C3%B3gica+conectivos>

!!! tip "Próxima Parada 🚏"
    Vamos praticar combinando conectivos em
    **[Aplicação das tabelas-verdade em exercícios](05-aula.md)**.
