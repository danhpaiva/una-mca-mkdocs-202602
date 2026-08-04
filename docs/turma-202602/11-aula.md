# 11. Aula de atividades e/ou prática de aplicação — Parte 2

!!! info "Nesta aula"
    - Aula prática, sem conteúdo novo.
    - Foco em **circuitos digitais** e revisão geral.
    - Consolidação de tudo antes de seguirmos para grafos.

## 🎯 Objetivo do encontro

Última aula prática antes de seguirmos para grafos. O foco aqui é circuitos
digitais ([Aula 09](09-aula.md)) e revisão integrada de tudo desde a
[Aula 03](03-aula.md).

## 🛠️ Roteiro da prática

??? abstract "Bloco 1 — Circuitos (20 min)"
    1. Dada a especificação "a saída é 1 quando exatamente uma das duas
       entradas é 1", monte a tabela-verdade, a expressão SOP e identifique a
       porta lógica correspondente.
    2. Implemente um **meio somador** em Python e teste as 4 combinações de
       entrada.
    3. Desafio: implemente o `full_adder` do Exercício 4 da
       [Aula 09](09-aula.md), se ainda não fez.

    !!! example "Gabarito do item 1, para autocorreção"
        A especificação descreve o **XOR**: $f = A\overline{B} + \overline{A}B$.
        Tabela-verdade: `(0,0)->0`, `(0,1)->1`, `(1,0)->1`, `(1,1)->0`.
        Porta correspondente: **XOR** (⊕), já vista na
        [Aula 06](06-aula.md) e usada no meio somador da
        [Aula 09](09-aula.md).

??? abstract "Bloco 2 — Revisão integrada (25 min)"
    Resolva, sem consultar as aulas:

    1. Uma tabela-verdade de 3 variáveis com pelo menos dois conectivos.
    2. Uma simplificação booleana usando axiomas.
    3. A mesma simplificação usando K-map.

    Só depois confira com as aulas correspondentes.

??? abstract "Bloco 3 — Check-in de progresso (15 min)"
    Em duplas, compartilhem:

    - Qual tema da disciplina até agora achou mais difícil, e por quê.
    - Um exercício que ainda não conseguiram resolver sozinhos.
    - Um plano concreto para revisar esse ponto antes da próxima aula.

## ✅ Checklist de saída

!!! check "Antes de sair da aula, confira"
    - [ ] Meio somador (e, se possível, somador completo) funcionando em
      Python.
    - [ ] Os três exercícios do Bloco 2 resolvidos e conferidos.
    - [ ] Lista de dúvidas para revisar antes de seguirmos para grafos.

## 📚 Referências

**Revisão de conteúdo**

- [Aula 06 e 07 — Álgebra Booleana](06-aula.md)
- [Aula 09 — Circuitos digitais](09-aula.md)

**🎥 Vídeos**

- Revisão de portas lógicas, meio somador e somador completo:
  <https://www.youtube.com/results?search_query=meio+somador+somador+completo+portas+l%C3%B3gicas+revis%C3%A3o>

!!! tip "Próxima Parada 🚏"
    Seguimos o conteúdo com
    **[Introdução a Grafos](12-aula.md)**.
