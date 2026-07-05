# 🚀 Lista 01 — Conjuntos

!!! abstract "Missão"
    Colocar em prática as operações de conjuntos da **[Aula 01](../aulas/01-aula.md)**,
    implementando cada exercício em **Python** e entregando o código em um
    repositório público no GitHub.

## 🎯 Objetivo

Consolidar união, interseção, diferença, complemento, pertinência e
compreensão — traduzindo a notação matemática em código.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** no GitHub chamado **`una-mca-lista01`**.
2. **Clone** o repositório na sua máquina:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista01.git
   cd una-mca-lista01
   ```
3. Resolva os exercícios (um arquivo `.py` por exercício, veja a estrutura abaixo).
4. **Suba o código** (commit + push):
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 01"
   git push origin main
   ```
5. **Entregue o link** do repositório na tarefa correspondente do **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público** antes de entregar o link.

## 📝 Exercícios

??? abstract "Exercício 1 — Operações básicas"
    Dados $A = \{1,2,3,4,5\}$ e $B = \{2,4,6,8\}$, imprima $A \cup B$, $A \cap B$,
    $A - B$ e $B - A$.

??? abstract "Exercício 2 — Compreensão"
    Gere, por compreensão, o conjunto dos múltiplos de 3 entre 1 e 30.

??? abstract "Exercício 3 — De Morgan"
    Com $\mathcal{U} = \{1,\dots,10\}$, verifique em código que
    $\overline{A \cup B} = \overline{A} \cap \overline{B}$.

??? abstract "Exercício 4 — Diferença simétrica"
    Implemente `simetrica(A, B)` **sem** usar `^` e compare com `A ^ B`.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista01/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** com o nome `una-mca-lista01`.
    - [ ] Um arquivo por exercício, com nomes claros.
    - [ ] Todos os códigos **rodam sem erro**.
    - [ ] `README.md` explica o que cada arquivo faz.
    - [ ] Commit com mensagem descritiva e `push` feito.
    - [ ] Link do repositório entregue no **Google Classroom**.
