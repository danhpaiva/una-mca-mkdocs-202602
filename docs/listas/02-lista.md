# 🚀 Lista 02 — Relações

!!! abstract "Missão"
    Aplicar os conceitos da **[Aula 02](../aulas/02-aula.md)**: produto cartesiano,
    relações e suas propriedades, implementando tudo em **Python**.

## 🎯 Objetivo

Gerar produtos cartesianos e verificar se uma relação é reflexiva, simétrica,
transitiva — e, portanto, de equivalência ou de ordem.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista02`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista02.git
   cd una-mca-lista02
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 02"
   git push origin main
   ```
5. **Entregue o link** do repositório no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Garanta que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Produto cartesiano"
    Gere e conte $A \times B$ para $A = \{a,b,c\}$ e $B = \{0,1\}$ (use `itertools.product`).

??? abstract "Exercício 2 — Propriedades"
    Implemente `reflexiva`, `simetrica` e `transitiva` e teste com pelo menos duas
    relações diferentes.

??? abstract "Exercício 3 — Equivalência"
    Verifique se "mesmo resto na divisão por 3" sobre $\{0,\dots,8\}$ é de
    equivalência e imprima suas classes.

??? abstract "Exercício 4 — Ordem"
    Classifique $\le$ sobre $\{1,2,3,4\}$: implemente as verificações e conclua se
    é relação de ordem.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista02/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista02`.
    - [ ] Um arquivo por exercício.
    - [ ] Códigos rodam sem erro e imprimem resultados claros.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
