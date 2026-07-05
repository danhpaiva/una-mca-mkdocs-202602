# 🚀 Lista 12 — Indução e recorrência

!!! abstract "Missão"
    Provar propriedades por indução e implementar recorrências da
    **[Aula 12](../aulas/12-aula.md)**, usando **Python**.

## 🎯 Objetivo

Escrever provas por indução (no `README.md`) e traduzir recorrências em funções
recursivas, incluindo otimização por memoização.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista12`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista12.git
   cd una-mca-lista12
   ```
3. Resolva os exercícios (provas no `README.md`; código em `.py`).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 12"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Indução (prova escrita)"
    Prove por indução que $1 + 3 + 5 + \dots + (2n-1) = n^2$. Escreva a prova
    completa (caso base + passo) no `README.md`.

??? abstract "Exercício 2 — Recorrência"
    Escreva a recorrência da soma dos $n$ primeiros naturais e implemente-a de
    forma recursiva em Python.

??? abstract "Exercício 3 — Desigualdade"
    Prove por indução que $2^n > n$ para $n \ge 1$ (prova no `README.md`) e
    escreva um teste em Python que confirme para $n$ até 20.

??? abstract "Exercício 4 — Fibonacci com memoização"
    Implemente `fib` ingênua e `fib_memo` (com `functools.lru_cache`) e compare os
    tempos para `fib(35)` usando `time`.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista12/
├── README.md          # provas por indução dos ex. 1 e 3
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista12`.
    - [ ] Provas por indução escritas de forma clara no `README.md`.
    - [ ] Códigos recursivos com **caso base** correto (sem recursão infinita).
    - [ ] Comparação de tempos do Fibonacci documentada.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
