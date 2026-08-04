# 08. Aula de atividades e/ou prática de aplicação — Parte 1

!!! info "Nesta aula"
    - Aula prática, sem conteúdo novo.
    - Consolidação de **lógica proposicional** e **álgebra booleana**.
    - Trabalho guiado, em dupla ou individual, com correção em sala.

## 🎯 Objetivo do encontro

Esta é uma aula de **bancada**: em vez de conteúdo novo, você aplica o que foi
visto nas [Aulas 03](03-aula.md) a [07](07-aula.md) em problemas guiados,
com o professor disponível para tirar dúvidas em tempo real.

!!! tip "Como aproveitar melhor"
    - Traga um notebook com Python configurado (veja
      [Ferramentas](../ferramentas.md)).
    - Tente resolver **sem consultar a aula** primeiro; só depois confira.
    - Se travar por mais de 10 minutos num item, chame o professor — não
      acumule dúvida.

## 🛠️ Roteiro da prática

??? abstract "Bloco 1 — Tabelas-verdade (15 min)"
    1. Monte, à mão, a tabela-verdade de $(p \to q) \wedge (q \to r)$.
    2. Confira o resultado escrevendo a função equivalente em Python e usando
       `itertools.product` (veja a [Aula 05](05-aula.md)).
    3. Classifique a fórmula: tautologia, contradição ou contingência?

    !!! example "Como conferir se você acertou"
        ```python
        from itertools import product

        def implica(p, q):
            return (not p) or q

        def formula(p, q, r):
            return implica(p, q) and implica(q, r)

        for p, q, r in product([True, False], repeat=3):
            print(p, q, r, "->", formula(p, q, r))
        ```
        Se pelo menos uma linha der `False`, a fórmula é uma
        **contingência** — não uma tautologia. Confira quantas linhas dão
        `False` na sua tabela feita à mão antes de rodar o código.

??? abstract "Bloco 2 — Simplificação booleana (20 min)"
    1. Simplifique algebricamente: $\overline{x}\,y + x\,y + x\,\overline{y}$.
    2. Confira sua simplificação com a função `equivalentes` da
       [Aula 06](06-aula.md).
    3. Desenhe o K-map da mesma expressão ([Aula 07](07-aula.md)) e confirme
       que chega ao mesmo resultado.

??? abstract "Bloco 3 — Mini-projeto (25 min)"
    Escreva um script Python que:

    1. Receba uma expressão booleana de 3 variáveis como uma função
       `lambda x, y, z: ...`.
    2. Gere a tabela-verdade completa.
    3. Imprima a **soma de produtos (SOP)** correspondente às linhas onde a
       função vale 1.

    Teste com pelo menos duas expressões diferentes.

## ✅ Checklist de saída

!!! check "Antes de sair da aula, confira"
    - [ ] Tabela-verdade do Bloco 1 batendo com o código.
    - [ ] Simplificação do Bloco 2 confirmada por `equivalentes`.
    - [ ] Script do Bloco 3 funcionando para pelo menos 2 expressões.
    - [ ] Dúvidas registradas para revisão futura.

## 📚 Referências

**Revisão de conteúdo**

- [Aula 03 — Fundamentos de lógica](03-aula.md)
- [Aula 04 — Conectivos e tabela-verdade](04-aula.md)
- [Aula 05 — Aplicação em exercícios](05-aula.md)
- [Aula 06 — Álgebra Booleana Parte 1](06-aula.md)
- [Aula 07 — Álgebra Booleana Parte 2](07-aula.md)

**Ferramentas de apoio**

- Python Tutor — visualize passo a passo a execução do seu código:
  <https://pythontutor.com/>
- SymPy — para conferir simplificações booleanas automaticamente:
  <https://docs.sympy.org/latest/modules/logic.html>

**🎥 Vídeos**

- Exercícios resolvidos combinando lógica e álgebra booleana:
  <https://www.youtube.com/results?search_query=exerc%C3%ADcios+resolvidos+l%C3%B3gica+e+%C3%A1lgebra+booleana>

!!! tip "Próxima Parada 🚏"
    Seguimos o conteúdo com
    **[Introdução a circuitos digitais](09-aula.md)**.
