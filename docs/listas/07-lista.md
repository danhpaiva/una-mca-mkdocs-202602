# 🚀 Lista 07 — Circuitos digitais

!!! abstract "Missão"
    Simular portas lógicas e somadores, com base na
    **[Aula 07](../aulas/07-aula.md)**, implementando em **Python**.

## 🎯 Objetivo

Traduzir tabelas-verdade em circuitos, simular meio somador e somador completo, e
compreender a universalidade da porta NAND.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista07`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista07.git
   cd una-mca-lista07
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 07"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Circuito XOR"
    Implemente $f = \overline{A}B + A\overline{B}$ e mostre que equivale ao XOR.

??? abstract "Exercício 2 — Full adder"
    Implemente `full_adder(a, b, c_in)` e imprima sua tabela-verdade completa.

??? abstract "Exercício 3 — NAND universal"
    Construa NOT, AND e OR usando **apenas** a porta NAND e teste cada um.

??? abstract "Exercício 4 — Somador de 4 bits"
    Some $0110_2$ e $0101_2$ com `soma_4bits`, exiba o resultado binário e decimal
    e explique o carry final.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista07/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista07`.
    - [ ] Um arquivo por exercício.
    - [ ] Tabelas-verdade dos circuitos impressas.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
