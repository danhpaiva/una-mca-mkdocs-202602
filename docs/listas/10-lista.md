# 🚀 Lista 10 — Matrizes

!!! abstract "Missão"
    Implementar operações com matrizes da **[Aula 10](../aulas/10-aula.md)** em
    **Python** (sem e com NumPy).

## 🎯 Objetivo

Somar, transpor e multiplicar matrizes, entendendo as restrições de dimensão e a
não comutatividade do produto.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista10`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista10.git
   cd una-mca-lista10
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 10"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Soma"
    Some $\begin{bmatrix}1&2\\3&4\end{bmatrix}$ e $\begin{bmatrix}5&6\\7&8\end{bmatrix}$
    com uma função própria (sem NumPy).

??? abstract "Exercício 2 — Produto e comutatividade"
    Calcule $A \cdot B$ e $B \cdot A$ para as matrizes acima e mostre que diferem.

??? abstract "Exercício 3 — Transposta"
    Implemente `transposta(M)` e aplique em $\begin{bmatrix}1&2&3\\4&5&6\end{bmatrix}$.

??? abstract "Exercício 4 — Identidade"
    Implemente `eh_identidade(M)` e teste com matrizes $3 \times 3$ (identidade e
    não-identidade). Refaça a multiplicação usando NumPy (`@`).

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista10/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista10`.
    - [ ] Um arquivo por exercício.
    - [ ] Funções próprias funcionam **sem** depender só de NumPy.
    - [ ] `README.md` documenta a lista (inclua como instalar o NumPy, se usado).
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
