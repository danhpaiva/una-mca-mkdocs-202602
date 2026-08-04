# 06. Álgebra Booleana e suas aplicações — Parte 1

!!! info "Nesta aula"
    - Da tabela-verdade para a álgebra sobre {0, 1}.
    - Axiomas e teoremas fundamentais.
    - Simplificação algébrica de expressões.
    - Base em Python com operadores bit a bit.

## 🔢 Da lógica para a álgebra

Na [Aula 04](04-aula.md) trabalhamos com V/F. A **álgebra booleana** é a mesma
estrutura, só que com **1** (verdadeiro) e **0** (falso), e três operações:

| Operação | Notação | Equivalente lógico |
| :--- | :--- | :--- |
| Produto (AND) | $x \cdot y$ ou $xy$ | $x \wedge y$ |
| Soma (OR) | $x + y$ | $x \vee y$ |
| Complemento (NOT) | $\overline{x}$ | $\neg x$ |

!!! warning "Cuidado com os símbolos"
    $+$ e $\cdot$ **não** são a soma e a multiplicação da aritmética comum!
    $1 + 1 = 1$ (não 2), porque aqui $+$ significa $\vee$.

## 📏 Axiomas e teoremas

=== "Identidade"
    $$x + 0 = x \qquad x \cdot 1 = x$$

=== "Complemento"
    $$x + \overline{x} = 1 \qquad x \cdot \overline{x} = 0$$

=== "Idempotência"
    $$x + x = x \qquad x \cdot x = x$$

=== "Absorção"
    $$x + xy = x \qquad x(x + y) = x$$

=== "Distributiva"
    $$x(y + z) = xy + xz \qquad x + yz = (x+y)(x+z)$$
    A segunda forma (distribuir $+$ sobre $\cdot$) não existe na aritmética
    comum — é uma particularidade da álgebra booleana, útil para "abrir" um
    termo como fizemos no exemplo de absorção logo abaixo.

=== "De Morgan"
    $$\overline{x + y} = \overline{x}\cdot\overline{y}
    \qquad
    \overline{x \cdot y} = \overline{x} + \overline{y}$$

!!! note "Princípio da dualidade"
    Toda identidade booleana continua válida se trocarmos $\cdot
    \leftrightarrow +$ e $0 \leftrightarrow 1$ ao mesmo tempo. A dual de
    $x + 0 = x$ é $x \cdot 1 = x$ — os axiomas sempre vêm aos pares.

## ✂️ Simplificando expressões

Simplificar reduz o número de operações — o que, na próxima aula (circuitos),
significa **menos portas lógicas** e hardware mais barato.

!!! example "Fatorando um complemento"
    $$xy + x\overline{y} = x\,(y + \overline{y}) = x \cdot 1 = x$$
    Fatoramos $x$, aplicamos o axioma do complemento ($y + \overline{y} = 1$)
    e a identidade ($x \cdot 1 = x$). Duas parcelas viraram um único literal.

!!! example "Usando absorção"
    $$x + \overline{x}y = (x + \overline{x})(x + y) = 1 \cdot (x + y) = x + y$$
    Distribuímos (forma dual), aplicamos complemento e identidade.

!!! example "Um caso com três termos (eliminando o consenso)"
    Simplifique $xy + \overline{x}z + yz$:

    1. O termo $yz$ é **redundante**: sempre que $yz = 1$ (ou seja, $y=1$ e
       $z=1$), pelo menos um de $xy$ ou $\overline{x}z$ também vale 1 —
       porque $x$ só pode ser 0 ou 1, e em qualquer caso um dos dois
       primeiros termos "cobre" essa situação.
    2. Confirme por tabela-verdade: monte as 8 linhas de
       $xy + \overline{x}z + yz$ e de $xy + \overline{x}z$ e compare a
       coluna de resultado — elas são **idênticas**.

    $$xy + \overline{x}z + yz = xy + \overline{x}z$$

    Esse é o **teorema do consenso**: o termo "de consenso" ($yz$, formado
    pelas variáveis que sobram de $x$ e $\overline{x}$) sempre pode ser
    eliminado.

## 🐍 Álgebra booleana em Python

```python
def AND(x, y): return x & y
def OR(x, y):  return x | y
def NOT(x):    return 1 - x

# Verificando que xy + x·NOT(y) simplifica para x
def original(x, y):
    return OR(AND(x, y), AND(x, NOT(y)))

def simplificada(x, y):
    return x

for x in (0, 1):
    for y in (0, 1):
        assert original(x, y) == simplificada(x, y)
print("Simplificação confirmada para todos os casos!")
```

!!! tip "Testando equivalência automaticamente"
    ```python
    from itertools import product

    def equivalentes(f, g, n):
        return all(f(*b) == g(*b) for b in product((0, 1), repeat=n))

    print(equivalentes(original, simplificada, 2))  # True
    ```

## 📝 Exercícios

??? abstract "Exercício 1"
    Monte a tabela-verdade de $f(x,y) = \overline{x} + y$. Compare com a
    tabela de $x \to y$ da [Aula 04](04-aula.md).

??? abstract "Exercício 2"
    Simplifique $xy + x\overline{y} + \overline{x}y$ usando os teoremas
    (dica: agrupe os dois primeiros termos primeiro).

??? abstract "Exercício 3"
    Use De Morgan para reescrever $\overline{xy + z}$ sem barra sobre grupos.

??? abstract "Exercício 4 — Desafio"
    Implemente `NAND(x, y)` e `NOR(x, y)` em Python e use `equivalentes` para
    confirmar $\overline{x \cdot y} = \overline{x} + \overline{y}$.

## 📚 Referências

**Livros (teoria)**

- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. AMGH/McGraw-Hill
  — cap. **Álgebra Booleana**.
- GERSTING, J. L. *Fundamentos Matemáticos para a Ciência da Computação*.
  7. ed. LTC — cap. **Álgebra de Boole e Computação**.
- IDOETA, I. V.; CAPUANO, F. G. *Elementos de Eletrônica Digital*. Érica —
  cap. **Álgebra de Boole e simplificação**.

**Documentação e prática (Python)**

- Python — operadores bit a bit `&`, `|`, `~`: <https://docs.python.org/3/reference/expressions.html#binary-bitwise-operations>

**🎥 Vídeos**

- Álgebra booleana — axiomas e simplificação passo a passo:
  <https://www.youtube.com/results?search_query=%C3%A1lgebra+booleana+axiomas+simplifica%C3%A7%C3%A3o+de+express%C3%B5es>
- Teorema do consenso e simplificação booleana avançada:
  <https://www.youtube.com/results?search_query=teorema+do+consenso+%C3%A1lgebra+booleana>

!!! tip "Próxima Parada 🚏"
    Continuamos em
    **[Álgebra Booleana e suas aplicações — Parte 2](07-aula.md)**, com mapas
    de Karnaugh — um atalho visual para simplificar expressões.
