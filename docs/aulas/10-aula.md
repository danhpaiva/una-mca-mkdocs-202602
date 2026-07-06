# 10. Matrizes

!!! info "Nesta aula"
    - O que é uma matriz e sua notação.
    - Operações: soma, multiplicação por escalar e produto.
    - Matriz identidade e transposta.
    - Matrizes na Computação (imagens, grafos, transformações).

## 🔲 O que é uma matriz

Uma **matriz** $m \times n$ é uma tabela de números com $m$ linhas e $n$ colunas.
O elemento na linha $i$, coluna $j$ é $a_{ij}$.

$$A = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}$$

## ➕ Operações básicas

=== "Soma"
    Elemento a elemento (matrizes de **mesma** dimensão):
    $$(A + B)_{ij} = a_{ij} + b_{ij}$$

=== "Escalar"
    Multiplica cada elemento:
    $$(kA)_{ij} = k \cdot a_{ij}$$

=== "Transposta"
    Troca linhas por colunas:
    $$(A^{T})_{ij} = a_{ji}$$

## ✖️ Produto de matrizes

O produto $C = A \cdot B$ existe quando o nº de **colunas** de $A$ = nº de
**linhas** de $B$. Cada elemento é um produto escalar de linha por coluna:

$$c_{ij} = \sum_{k=1}^{n} a_{ik}\, b_{kj}$$

!!! warning "Não é comutativo!"
    Em geral $A \cdot B \neq B \cdot A$. Além disso, a ordem das dimensões
    importa: $(m \times n)\cdot(n \times p) = (m \times p)$.

!!! example "Produto passo a passo (e AB ≠ BA)"
    Com $A = \begin{bmatrix}1&2\\3&4\end{bmatrix}$ e $B = \begin{bmatrix}5&6\\7&8\end{bmatrix}$:

    $$c_{11} = 1\cdot 5 + 2\cdot 7 = 19 \qquad c_{12} = 1\cdot 6 + 2\cdot 8 = 22$$
    $$A\cdot B = \begin{bmatrix}19&22\\43&50\end{bmatrix}
    \qquad
    B\cdot A = \begin{bmatrix}23&34\\31&46\end{bmatrix}$$

    Diferentes! Cada elemento $c_{ij}$ é "linha $i$ de $A$ vezes coluna $j$ de $B$".

## 🆔 Matriz identidade

A identidade $I$ tem 1 na diagonal e 0 no resto; funciona como o "1" da
multiplicação: $A \cdot I = A$.

$$I_3 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$

!!! tip "Testando se uma matriz é a identidade"
    $M$ é identidade se for **quadrada** e $M_{ij} = 1$ quando $i = j$ e $0$ caso
    contrário. É a condição que a função `eh_identidade` do desafio deve verificar.

### Transposta na prática

$(A^{T})_{ij} = a_{ji}$: a linha $i$ vira a coluna $i$. Uma matriz $2 \times 3$
transposta vira $3 \times 2$:

$$\begin{bmatrix}1&2&3\\4&5&6\end{bmatrix}^{T} = \begin{bmatrix}1&4\\2&5\\3&6\end{bmatrix}$$

## 🐍 Matrizes em Python

Com listas de listas:

```python
def multiplica(A, B):
    linhas_A, colunas_A = len(A), len(A[0])
    colunas_B = len(B[0])
    C = [[0] * colunas_B for _ in range(linhas_A)]
    for i in range(linhas_A):
        for j in range(colunas_B):
            for k in range(colunas_A):
                C[i][j] += A[i][k] * B[k][j]
    return C

A = [[1, 2], [3, 4]]
B = [[5, 6], [7, 8]]
print(multiplica(A, B))   # [[19, 22], [43, 50]]
```

!!! tip "Na prática, use NumPy"
    ```python
    import numpy as np
    A = np.array([[1, 2], [3, 4]])
    B = np.array([[5, 6], [7, 8]])
    print(A @ B)        # produto
    print(A.T)          # transposta
    ```

## 🌍 Aplicações na Computação

- **Imagens:** um bitmap é uma matriz de pixels.
- **Grafos:** a **matriz de adjacência** (próxima aula!) representa conexões.
- **Computação gráfica:** rotações e escalas são multiplicações por matrizes.
- **IA:** redes neurais são, no fundo, muitas multiplicações de matrizes.

## 📝 Exercícios

??? abstract "Exercício 1"
    Some $\begin{bmatrix}1&2\\3&4\end{bmatrix}$ e $\begin{bmatrix}5&6\\7&8\end{bmatrix}$
    à mão e confira em Python.

??? abstract "Exercício 2"
    Calcule $A \cdot B$ e $B \cdot A$ para as matrizes acima. Elas são iguais?

??? abstract "Exercício 3"
    Escreva a transposta de $\begin{bmatrix}1&2&3\\4&5&6\end{bmatrix}$.

??? abstract "Exercício 4 — Desafio"
    Implemente `transposta(M)` e `eh_identidade(M)` sem NumPy. Teste com matrizes
    $3 \times 3$.

## 📚 Referências

**Livros (teoria)**

- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. AMGH/McGraw-Hill —
  seção sobre **matrizes** (operações e aplicações).
- GERSTING, J. L. *Fundamentos Matemáticos para a Ciência da Computação*. 7. ed.
  LTC — cap. **Relações, Funções e Matrizes**.
- BOLDRINI, J. L. et al. *Álgebra Linear*. Harbra — cap. **Matrizes e operações**.
- STEINBRUCH, A.; WINTERLE, P. *Álgebra Linear*. Pearson — **matrizes e produto matricial**.

**Documentação e prática (Python)**

- NumPy — guia do usuário (arrays e `@`): <https://numpy.org/doc/stable/user/absolute_beginners.html>
- NumPy — `numpy.matmul` / operador `@`: <https://numpy.org/doc/stable/reference/generated/numpy.matmul.html>

!!! tip "Próxima Parada 🚏"
    Vá para a **[Lista 10 — Matrizes](../listas/10-lista.md)**. Usaremos matrizes
    logo em seguida para representar **[Grafos e árvores](11-aula.md)**.
