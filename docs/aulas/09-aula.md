# 09. Combinatória

!!! info "Nesta aula"
    - Fatorial.
    - Permutações (a ordem importa).
    - Arranjos e combinações.
    - Binômio e triângulo de Pascal.

## ❗ Fatorial

$$n! = n \cdot (n-1) \cdot (n-2) \cdots 2 \cdot 1, \qquad 0! = 1$$

Conta de quantas formas ordenamos $n$ objetos distintos.

## 🔀 Permutação, arranjo e combinação

A pergunta-chave é sempre: **a ordem importa?**

=== "Permutação (ordena tudo)"
    Todas as ordenações de $n$ objetos:
    $$P(n) = n!$$
    Ex.: quantas filas com 4 pessoas? $4! = 24$.

=== "Arranjo (ordena k de n)"
    Escolhe **e ordena** $k$ dentre $n$:
    $$A(n,k) = \frac{n!}{(n-k)!}$$
    Ex.: pódio (ouro/prata/bronze) com 8 atletas: $A(8,3) = 336$.

=== "Combinação (só escolhe k de n)"
    Escolhe $k$ dentre $n$ **sem** ordem:
    $$C(n,k) = \binom{n}{k} = \frac{n!}{k!\,(n-k)!}$$
    Ex.: comissão de 3 entre 8: $C(8,3) = 56$.

!!! tip "Arranjo vs. Combinação"
    Arranjo = combinação **vezes** as ordenações internas: $A(n,k) = C(n,k)\cdot k!$.
    Se trocar a ordem gera um caso **novo**, é arranjo; se não, é combinação.

### E quando há repetição?

- **Sequências com repetição permitida** (ex.: senhas com dígitos que podem
  repetir): pelo princípio multiplicativo, são $n^k$ (visto na
  [Aula 08](08-aula.md)).
- **Permutação com elementos repetidos** (anagramas): se um objeto se repete, as
  trocas entre iguais não contam. As permutações de $n$ objetos com grupos de
  tamanhos $n_1, n_2, \dots$ são
  $$\dfrac{n!}{n_1!\,n_2!\cdots}$$
  Ex.: anagramas de "ARARA" (3 A, 2 R): $\dfrac{5!}{3!\,2!} = 10$.

!!! warning "\"Sem repetição\" costuma ser arranjo"
    Uma senha de 4 dígitos **sem repetir** dígito é um **arranjo** $A(10,4)$, não
    uma combinação — porque a ordem dos dígitos importa (`1234` ≠ `4321`).

## 🔺 Triângulo de Pascal

Os coeficientes binomiais formam o triângulo, onde cada número é a soma dos dois
acima:

```
n=0:          1
n=1:        1   1
n=2:      1   2   1
n=3:    1   3   3   1
n=4:  1   4   6   4   1
```

Vale a **relação de Pascal**:

$$\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$$

E o **binômio de Newton**:

$$(a + b)^n = \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^{k}$$

!!! example "Expandindo $(x + y)^4$"
    Os coeficientes são a linha $n=4$ do triângulo: $1, 4, 6, 4, 1$.
    $$(x+y)^4 = x^4 + 4x^3y + 6x^2y^2 + 4xy^3 + y^4$$
    Repare que os expoentes de $x$ **caem** de 4 a 0 enquanto os de $y$ **sobem**,
    e sempre somam 4.

## 🐍 Combinatória em Python

O módulo `math` já traz tudo:

```python
from math import factorial, perm, comb

print(factorial(5))   # 120
print(perm(8, 3))     # 336  -> arranjo A(8,3)
print(comb(8, 3))     # 56   -> combinação C(8,3)
```

E o `itertools` **gera** as possibilidades:

```python
from itertools import permutations, combinations

print(list(permutations([1, 2, 3])))        # 6 tuplas ordenadas
print(list(combinations([1, 2, 3, 4], 2)))  # 6 pares sem ordem
```

!!! note "Conferindo a fórmula"
    `len(list(combinations(range(8), 3))) == comb(8, 3)` → `True`.

## 🌍 Aplicações

- **Loterias e probabilidade:** $C(n,k)$ no denominador.
- **Testes de software:** quantos pares/triplas de parâmetros combinar.
- **Grafos:** número de arestas possíveis num grafo com $n$ vértices é $\binom{n}{2}$.

## 📝 Exercícios

??? abstract "Exercício 1"
    Quantas senhas de 4 dígitos **sem repetição** existem? É arranjo ou combinação?

??? abstract "Exercício 2"
    De um grupo de 10 alunos, quantas comissões de 4 podem ser formadas?

??? abstract "Exercício 3"
    Expanda $(x + y)^4$ usando o binômio de Newton e confira os coeficientes no
    triângulo de Pascal.

??? abstract "Exercício 4 — Desafio"
    Implemente `combinacao(n, k)` **sem** usar `math.comb`, apenas com a relação
    de Pascal (recursão ou tabela). Compare com `math.comb`.

## 📚 Referências

**Livros (teoria)**

- MORGADO, A. C. et al. *Análise Combinatória e Probabilidade*. SBM — referência
  clássica de **permutações, arranjos e combinações**.
- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. AMGH/McGraw-Hill —
  cap. **Contagem** (combinações, permutações, binômio de Newton).
- HAZZAN, S. *Fundamentos de Matemática Elementar, vol. 5: Combinatória e
  Probabilidade*. Atual — muitos exercícios resolvidos.
- SANTOS, J. P. O. et al. *Introdução à Análise Combinatória*. Ciência Moderna.

**Documentação e prática (Python)**

- Python — `math.factorial`, `math.perm`, `math.comb`: <https://docs.python.org/3/library/math.html#number-theoretic-and-representation-functions>
- Python — `itertools.permutations` / `combinations`: <https://docs.python.org/3/library/itertools.html#itertools.permutations>

!!! tip "Próxima Parada 🚏"
    Pratique na **[Lista 09 — Combinatória](../listas/09-lista.md)**. Agora
    passamos a **estruturas de dados matemáticas** começando por
    **[Matrizes](10-aula.md)**.
