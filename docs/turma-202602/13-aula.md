# 13. Atividade avaliativa em grupo na sala

!!! danger "Página-modelo — ajuste antes de publicar"
    Tamanho dos grupos e peso na média são **placeholders**. Ajuste conforme
    o plano de ensino oficial da UC.

!!! info "Nesta aula"
    - Atividade avaliativa feita **em sala**, em grupo.
    - Problema aplicado, combinando lógica, álgebra booleana e grafos.
    - Rubrica de correção.

## 🎯 Formato

- Grupos de **3 a 4 pessoas**, formados no início da aula.
- Todo o grupo recebe o **mesmo problema**, resolvido e entregue **na própria
  aula**.
- Consulta permitida às aulas do curso (não à internet nem a colegas de
  outros grupos).

## 🧩 Problema proposto (modelo)

!!! example "Modelagem de um sistema de acesso"
    Uma sala segura libera a entrada quando: **(a)** o crachá é válido **e**
    **(b)** (a senha está correta **ou** há uma autorização de emergência
    ativa).

    O grupo deve, em conjunto:

    1. Traduzir a regra para uma fórmula lógica com proposições $p$
       (crachá válido), $q$ (senha correta), $r$ (autorização de
       emergência).
    2. Montar a tabela-verdade completa.
    3. Simplificar a expressão booleana equivalente (axiomas ou K-map).
    4. Modelar as **dependências de aprovação** dessa regra como um grafo
       dirigido (quem precisa validar o quê antes de liberar o acesso) e
       identificar se há algum ciclo problemático nessas dependências.

!!! note "Adapte o problema"
    O professor pode substituir o cenário (ex.: liberação de crédito,
    matrícula condicional, controle de estoque) mantendo a mesma estrutura:
    lógica → álgebra booleana → grafo de dependências.

!!! example "Variante alternativa (caso queira dois problemas em turmas grandes)"
    "Um pedido de compra é aprovado quando: **(a)** o valor é menor que
    R\$ 500, **ou** **(b)** (o valor é ≥ R\$ 500 **e** há aprovação do
    gerente **e** há aprovação financeira)."

    Com $p$ = "valor < R\$ 500", $q$ = "aprovação do gerente", $r$ =
    "aprovação financeira", a fórmula é $p \vee (\overline{p} \wedge q
    \wedge r)$. O grafo de dependências aqui é uma **cadeia de aprovação**
    (gerente → financeiro), útil para discutir se aprovações podem ocorrer
    em paralelo (grafo sem dependência direta) ou em sequência obrigatória
    (aresta dirigida entre as etapas).

## 🧾 Rubrica de correção

| Critério | Peso sugerido |
| :--- | :---: |
| Tradução correta da regra em lógica formal | 25% |
| Tabela-verdade correta | 20% |
| Simplificação booleana correta | 25% |
| Modelagem correta do grafo de dependências | 20% |
| Colaboração e clareza da entrega escrita | 10% |

## 🤝 Dicas para o trabalho em grupo

!!! tip "Como dividir sem perder a visão do todo"
    - Um integrante cuida da tradução lógica, outro da tabela-verdade, outro
      da simplificação e outro do grafo — mas **todos revisam tudo** antes
      de entregar.
    - Se o grupo discordar de um passo, refaçam juntos a tabela-verdade: ela
      é o "juiz" objetivo de qualquer simplificação.
    - Entreguem mesmo que incompleto — parcial correto vale mais que
      completo errado.

## 📝 Antes de sair da aula

!!! check "Checklist de entrega"
    - [ ] Fórmula lógica da regra, com legenda das proposições.
    - [ ] Tabela-verdade completa.
    - [ ] Expressão simplificada, com os passos.
    - [ ] Grafo de dependências desenhado, com análise de ciclo.
    - [ ] Nome de todos os integrantes do grupo na entrega.

## 📚 Referências

**Conteúdo aplicado na atividade**

- [Aulas 04 e 05 — Lógica e tabela-verdade](04-aula.md)
- [Aulas 06 e 07 — Álgebra Booleana](06-aula.md)
- [Aula 12 — Introdução a Grafos](12-aula.md)

**Sobre trabalho em equipe**

- KATZENBACH, J. R.; SMITH, D. K. *A Sabedoria das Equipes*. Best Seller —
  clássico sobre como pequenas equipes funcionam bem.

**🎥 Vídeos**

- Como dividir tarefas em um trabalho em grupo técnico sem perder a visão
  do todo:
  <https://www.youtube.com/results?search_query=como+dividir+tarefas+trabalho+em+grupo+programa%C3%A7%C3%A3o>

!!! tip "Próxima Parada 🚏"
    Grafos preparam o terreno para
    **[Estudo de Árvore](14-aula.md)** — um tipo especial de grafo.
