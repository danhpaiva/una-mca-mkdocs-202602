# 06. Álgebra booleana

!!! info "Nesta aula"
    - Valores e operações booleanas.
    - Axiomas e teoremas (identidade, complemento, De Morgan).
    - Funções booleanas e sua forma normal.
    - Simplificação de expressões.

## 🔢 O universo {0, 1}

A **álgebra booleana** trabalha com apenas dois valores — $0$ (falso) e $1$
(verdadeiro) — e três operações básicas:

| Operação | Notação | Equivalente lógico |
| :--- | :--- | :--- |
| Produto (AND) | $x \cdot y$ ou $xy$ | $x \wedge y$ |
| Soma (OR) | $x + y$ | $x \vee y$ |
| Complemento (NOT) | $\overline{x}$ | $\neg x$ |

!!! note "Cuidado com os símbolos"
    $+$ e $\cdot$ **não** são soma e multiplicação usuais! $1 + 1 = 1$ (não 2),
    porque $1 + 1$ significa $1 \vee 1$.

## 📏 Axiomas e teoremas

=== "Identidade"
    $$x + 0 = x \qquad x \cdot 1 = x$$

=== "Complemento"
    $$x + \overline{x} = 1 \qquad x \cdot \overline{x} = 0$$

=== "Idempotência"
    $$x + x = x \qquad x \cdot x = x$$

=== "Absorção"
    $$x + xy = x \qquad x(x + y) = x$$

=== "De Morgan"
    $$\overline{x + y} = \overline{x}\cdot\overline{y}
    \qquad
    \overline{x \cdot y} = \overline{x} + \overline{y}$$

## 🧮 Funções booleanas

Uma **função booleana** mapeia combinações de bits em $\{0,1\}$. Ela pode ser
descrita por uma **tabela-verdade** e por uma **expressão**.

Exemplo: $f(x, y) = x \cdot \overline{y} + \overline{x} \cdot y$ (isto é o **XOR**):

| $x$ | $y$ | $f(x,y)$ |
| :-: | :-: | :-: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

## ✂️ Simplificação

Simplificar reduz o número de operações (⇒ circuitos menores e mais baratos).
Exemplo aplicando **absorção**:

$$f = x + \overline{x}y = x + y$$

*Passo a passo:* $x + \overline{x}y = (x + \overline{x})(x + y) = 1 \cdot (x + y) = x + y$.

## 🐍 Álgebra booleana em Python

```python
def AND(x, y): return x & y
def OR(x, y):  return x | y
def NOT(x):    return 1 - x

def xor(x, y):
    # x·ȳ + x̄·y
    return OR(AND(x, NOT(y)), AND(NOT(x), y))

for x in (0, 1):
    for y in (0, 1):
        print(x, y, "->", xor(x, y))
```

!!! tip "Verificando uma simplificação"
    Duas expressões são equivalentes se produzem a **mesma** tabela-verdade:

    ```python
    from itertools import product

    def equivalentes(f, g, n):
        return all(f(*b) == g(*b) for b in product((0, 1), repeat=n))

    f = lambda x, y: OR(x, AND(NOT(x), y))   # x + x̄y
    g = lambda x, y: OR(x, y)                 # x + y
    print(equivalentes(f, g, 2))              # True
    ```

## 📝 Exercícios

??? abstract "Exercício 1"
    Monte a tabela-verdade de $f(x,y) = \overline{x} + y$.

??? abstract "Exercício 2"
    Simplifique $x y + x \overline{y}$ usando os teoremas. (Dica: fatore $x$.)

??? abstract "Exercício 3"
    Use De Morgan para reescrever $\overline{xy + z}$ sem barra sobre grupos.

??? abstract "Exercício 4 — Desafio"
    Implemente `NAND` e `NOR` em Python e mostre, com `equivalentes`, que
    $\overline{x \cdot y} = \overline{x} + \overline{y}$.

!!! tip "Próxima Parada 🚏"
    Pratique na **[Lista 06 — Álgebra booleana](../listas/06-lista.md)**. Na
    sequência, essas expressões viram fios e portas em
    **[Circuitos digitais](07-aula.md)**.
