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

## 🆔 Matriz identidade

A identidade $I$ tem 1 na diagonal e 0 no resto; funciona como o "1" da
multiplicação: $A \cdot I = A$.

$$I_3 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$

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

!!! tip "Próxima Parada 🚏"
    Vá para a **[Lista 10 — Matrizes](../listas/10-lista.md)**. Usaremos matrizes
    logo em seguida para representar **[Grafos e árvores](11-aula.md)**.
