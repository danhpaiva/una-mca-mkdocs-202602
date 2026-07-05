# 🚀 Lista 09 — Combinatória

!!! abstract "Missão"
    Resolver problemas de permutação, arranjo e combinação da
    **[Aula 09](../aulas/09-aula.md)**, usando **Python**.

## 🎯 Objetivo

Decidir quando a ordem importa, aplicar fatorial/arranjo/combinação e explorar o
triângulo de Pascal.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista09`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista09.git
   cd una-mca-lista09
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 09"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Ordem importa?"
    Calcule quantas senhas de 4 dígitos **sem repetição** existem e justifique se
    é arranjo ou combinação (use `math.perm`).

??? abstract "Exercício 2 — Comissões"
    De 10 alunos, quantas comissões de 4 podem ser formadas? (use `math.comb`).

??? abstract "Exercício 3 — Binômio"
    Gere os coeficientes de $(x+y)^4$ e confira contra a linha $n=4$ do triângulo
    de Pascal.

??? abstract "Exercício 4 — Pascal sem math.comb"
    Implemente `combinacao(n, k)` usando **apenas** a relação de Pascal e compare
    com `math.comb`.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista09/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista09`.
    - [ ] Um arquivo por exercício.
    - [ ] Cada resposta indica se é arranjo/combinação e por quê.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
