# 🚀 Lista 11 — Grafos e árvores

!!! abstract "Missão"
    Representar e percorrer grafos e árvores da **[Aula 11](../aulas/11-aula.md)**,
    implementando em **Python**.

## 🎯 Objetivo

Modelar grafos com lista e matriz de adjacência, calcular graus, percorrer com
BFS/DFS e aplicar propriedades de árvores.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista11`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista11.git
   cd una-mca-lista11
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 11"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Modelagem"
    Represente, como lista de adjacência, o grafo $V=\{1,2,3,4\}$ com
    $E=\{\{1,2\},\{2,3\},\{3,4\},\{4,1\}\}$. É conexo? Tem ciclo?

??? abstract "Exercício 2 — Matriz e graus"
    Gere a matriz de adjacência do grafo acima, some os graus e comprove o
    **Handshake Lemma**.

??? abstract "Exercício 3 — Árvore"
    Escreva um programa que, dado o nº de vértices de uma árvore, retorne o nº de
    arestas ($n-1$) e explique por quê.

??? abstract "Exercício 4 — BFS e DFS"
    Implemente BFS e DFS e imprima a ordem de visita a partir de um mesmo vértice,
    comparando os resultados.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista11/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista11`.
    - [ ] Um arquivo por exercício.
    - [ ] BFS e DFS imprimem a ordem de visita.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
