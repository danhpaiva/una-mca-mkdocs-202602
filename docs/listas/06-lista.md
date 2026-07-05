# 🚀 Lista 06 — Álgebra booleana

!!! abstract "Missão"
    Manipular e simplificar expressões booleanas, com base na
    **[Aula 06](../aulas/06-aula.md)**, implementando em **Python**.

## 🎯 Objetivo

Aplicar operações e teoremas booleanos, montar tabelas-verdade de funções e
comprovar simplificações.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista06`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista06.git
   cd una-mca-lista06
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 06"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Tabela de função"
    Monte em código a tabela-verdade de $f(x,y) = \overline{x} + y$.

??? abstract "Exercício 2 — Simplificação"
    Comprove (comparando tabelas) que $xy + x\overline{y} = x$.

??? abstract "Exercício 3 — De Morgan"
    Verifique em código que $\overline{x \cdot y} = \overline{x} + \overline{y}$.

??? abstract "Exercício 4 — NAND/NOR"
    Implemente `NAND` e `NOR` e mostre com uma função `equivalentes` que
    $\overline{x + y} = \overline{x} \cdot \overline{y}$.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista06/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista06`.
    - [ ] Um arquivo por exercício.
    - [ ] Cada simplificação é comprovada por tabela-verdade.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
