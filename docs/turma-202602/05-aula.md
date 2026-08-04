# 05. Aplicação das tabelas-verdade em exercícios

!!! info "Nesta aula"
    - Montando tabelas-verdade de fórmulas com vários conectivos.
    - Tautologia, contradição e contingência.
    - Verificando tudo automaticamente em Python.

## 🧮 Fórmulas com múltiplos conectivos

Com $n$ proposições simples, uma tabela-verdade tem $2^n$ linhas — uma para
cada combinação possível de valores. Vamos montar a tabela de
$(p \wedge q) \to r$ passo a passo (3 variáveis → $2^3 = 8$ linhas):

| $p$ | $q$ | $r$ | $p \wedge q$ | $(p \wedge q) \to r$ |
| :-: | :-: | :-: | :-: | :-: |
| V | V | V | V | V |
| V | V | F | V | F |
| V | F | V | F | V |
| V | F | F | F | V |
| F | V | V | F | V |
| F | V | F | F | V |
| F | F | V | F | V |
| F | F | F | F | V |

!!! tip "Monte por colunas, não por linha"
    Preencha uma coluna auxiliar (aqui, $p \wedge q$) inteira antes de passar
    para a próxima. É mais fácil não errar do que calcular linha por linha.

## 🏷️ Tautologia, contradição e contingência

- **Tautologia**: a fórmula é **sempre verdadeira**, para qualquer combinação
  de valores.
- **Contradição**: a fórmula é **sempre falsa**.
- **Contingência**: depende dos valores — às vezes V, às vezes F.

!!! example "Reconhecendo cada tipo"
    - $p \vee \neg p$ → sempre V → **tautologia** (princípio do terceiro
      excluído).
    - $p \wedge \neg p$ → sempre F → **contradição**.
    - $p \to q$ → varia → **contingência**.

!!! note "Por que tautologias importam"
    Uma tautologia representa um raciocínio **válido por estrutura**,
    independente do assunto. $p \to (p \vee q)$ é tautologia: não importa o
    que $p$ e $q$ signifiquem, essa implicação nunca falha. É esse tipo de
    fórmula que sustenta regras de inferência confiáveis.

!!! example "Duas fórmulas 'iguais' por tabela-verdade: De Morgan"
    Monte lado a lado $\neg(p \wedge q)$ e $\neg p \vee \neg q$:

    | $p$ | $q$ | $\neg(p \wedge q)$ | $\neg p \vee \neg q$ |
    | :-: | :-: | :-: | :-: |
    | V | V | F | F |
    | V | F | V | V |
    | F | V | V | V |
    | F | F | V | V |

    As duas colunas finais são **idênticas** — as fórmulas são
    **logicamente equivalentes**, mesmo parecendo diferentes escritas. Essa é
    a **Lei de De Morgan**, e vamos reencontrá-la em forma de álgebra na
    [próxima aula](06-aula.md).

!!! example "Contingência no dia a dia: uma recomendação condicional"
    "Se chove **ou** está frio, leve casaco" — modelando $p$ = "chove",
    $q$ = "está frio", $r$ = "levo casaco", a regra ideal seria
    $r \leftrightarrow (p \vee q)$. Só que essa fórmula é uma
    **contingência**: ela pode ser V ou F dependendo se você realmente segue
    a recomendação ($r$) nas situações em que ela se aplica ($p \vee q$).
    Diferente de uma tautologia, aqui o valor da fórmula **depende de um
    fato do mundo real** (você ter levado o casaco ou não), não só da
    estrutura lógica.

## 🐍 Verificando tudo com Python

Em vez de montar a tabela à mão, geramos todas as combinações com
`itertools.product` e avaliamos a fórmula em cada uma:

```python
from itertools import product

def implica(p, q):
    return (not p) or q

def tabela_verdade(formula, n_variaveis):
    for valores in product([True, False], repeat=n_variaveis):
        resultado = formula(*valores)
        print(valores, "->", resultado)

# (p ^ q) -> r
formula = lambda p, q, r: implica(p and q, r)
tabela_verdade(formula, 3)
```

```python
def classificar(formula, n_variaveis):
    resultados = [formula(*v) for v in product([True, False], repeat=n_variaveis)]
    if all(resultados):
        return "tautologia"
    if not any(resultados):
        return "contradição"
    return "contingência"

print(classificar(lambda p: p or (not p), 1))       # tautologia
print(classificar(lambda p: p and (not p), 1))      # contradição
print(classificar(lambda p, q: implica(p, q), 2))   # contingência
```

!!! tip "Isso escala para qualquer número de variáveis"
    O mesmo `classificar` funciona para 4, 5 ou mais variáveis — só muda
    `n_variaveis`. É impraticável fazer isso à mão além de 3-4 variáveis, mas
    trivial em código.

## 📝 Exercícios

??? abstract "Exercício 1 — Montando à mão"
    Monte a tabela-verdade de $(p \vee q) \wedge \neg r$ (3 variáveis, 8
    linhas). Depois confira com `tabela_verdade` da aula.

??? abstract "Exercício 2 — Classificando"
    Classifique como tautologia, contradição ou contingência:
    (a) $(p \to q) \vee p$; (b) $(p \wedge q) \wedge \neg(p \vee q)$;
    (c) $p \leftrightarrow \neg p$.

??? abstract "Exercício 3 — Traduzindo e verificando"
    Modele "Se estudo e durmo bem, então passo" como uma fórmula de 3
    variáveis e use `tabela_verdade` para encontrar uma linha em que a
    fórmula é **falsa**.

??? abstract "Exercício 4 — Desafio"
    Escreva uma função `sao_equivalentes(f, g, n)` que devolva `True` quando
    duas fórmulas `f` e `g` de `n` variáveis produzirem a **mesma** coluna de
    resultados. Use-a para confirmar que $p \to q$ e $\neg p \vee q$ são
    equivalentes.

## 📚 Referências

**Livros (teoria)**

- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. AMGH/McGraw-Hill
  — cap. **Lógica Proposicional** (tautologias, contradições, contingências).
- GERSTING, J. L. *Fundamentos Matemáticos para a Ciência da Computação*.
  7. ed. LTC — cap. **Lógica**.
- SCHEINERMAN, E. R. *Matemática Discreta: uma introdução*. Cengage — seção
  sobre **tabelas-verdade e classificação de fórmulas**.

**Documentação e prática (Python)**

- Python — `itertools.product`: <https://docs.python.org/3/library/itertools.html#itertools.product>
- Python — `all()` e `any()`: <https://docs.python.org/3/library/functions.html#all>

**🎥 Vídeos**

- Exercícios resolvidos de tabela-verdade com tautologia, contradição e
  contingência:
  <https://www.youtube.com/results?search_query=exerc%C3%ADcios+tabela+verdade+tautologia+contradi%C3%A7%C3%A3o+conting%C3%AAncia>
- Leis de De Morgan explicadas com tabela-verdade:
  <https://www.youtube.com/results?search_query=leis+de+morgan+l%C3%B3gica+tabela+verdade>

!!! tip "Próxima Parada 🚏"
    Com lógica proposicional consolidada, entramos em
    **[Álgebra Booleana e suas aplicações — Parte 1](06-aula.md)**, onde essas
    mesmas tabelas viram álgebra sobre $\{0, 1\}$.
