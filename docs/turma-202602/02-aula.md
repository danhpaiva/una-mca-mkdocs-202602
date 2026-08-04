# 02. Busca Ativa — Início de Semestre

!!! info "Nesta aula"
    - O que é **Busca Ativa** e por que a instituição investe tempo de aula
      nisso.
    - Como a aula funciona na prática (o que o professor faz, o que você
      faz).
    - Um diagnóstico rápido de onboarding (ferramentas, acesso, dúvidas de
      ementa).
    - Um desafio lógico opcional para quem já está em dia.

## 🎯 O que é Busca Ativa

**Busca Ativa** é uma prática de acompanhamento estudantil: em vez de esperar
que um aluno que está sumindo das aulas ou atrasado nas atividades venha
pedir ajuda, a instituição e o professor **vão até ele** — via contato
direto, checagem de frequência e desempenho, e oferta concreta de suporte.
A ideia é simples: **problemas de engajamento detectados cedo são muito mais
fáceis de resolver do que problemas descobertos no fim do semestre**, quando
já não há tempo de recuperação.

!!! note "Por que logo na segunda aula?"
    Os primeiros encontros do semestre são o momento de maior risco de
    evasão: alunos que não conseguiram instalar as ferramentas, que ficaram
    com dúvida sobre a ementa, ou que simplesmente não conseguiram comparecer
    à Aula 01, tendem a se afastar ainda mais se ninguém os procurar agora.

## 🗓️ Como esta aula funciona

Esta é uma aula com **dinâmica diferente** das aulas de conteúdo:

=== "👩‍🏫 O professor"
    - Confere frequência e o checklist de onboarding da
      [Aula 01](01-aula.md) (Python, VS Code, Git instalados).
    - Contata individualmente quem faltou na Aula 01 ou não iniciou a
      configuração do ambiente.
    - Esclarece dúvidas de ementa, avaliação e cronograma que ainda não
      foram resolvidas.

=== "🧑‍🎓 Você"
    - Se está em dia: resolve o **diagnóstico de onboarding** abaixo e, se
      sobrar tempo, o desafio lógico opcional.
    - Se está atrasado: aproveite este momento para regularizar — é
      exatamente para isso que a aula existe, **sem julgamento**.
    - Se conhece um colega que sumiu, avise-o sobre esta aula: busca ativa
      funciona melhor com ajuda dos próprios colegas.

## 🧪 Diagnóstico rápido de onboarding

!!! check "Confira seu próprio status"
    - [ ] Python 3.10+ instalado e `python --version` funcionando no
      terminal.
    - [ ] VS Code instalado, com o projeto do curso aberto ao menos uma vez.
    - [ ] Git instalado, com `git config --global user.name` e
      `user.email` configurados.
    - [ ] Conta no GitHub criada.
    - [ ] Acesso confirmado ao canal oficial da turma (Google Classroom ou
      equivalente).
    - [ ] Dúvidas sobre a ementa ou a atividade avaliativa em grupo
      esclarecidas — veja a [Aula 01](01-aula.md) se precisar relembrar.

Se **qualquer** item ficou sem marcar, esta é a prioridade da aula de hoje —
antes de tudo o mais.

## 🧩 Para quem já está em dia (opcional)

Um desafio leve de raciocínio lógico, que antecipa o que vem na próxima aula
de conteúdo:

??? abstract "Desafio opcional — Quem usa qual fantasia?"
    Três amigos — **Ana**, **Bruno** e **Caio** — foram a um bloco de
    Carnaval do ano anterior, cada um com uma fantasia diferente: **pirata**,
    **super-herói** e **palhaço**. Sabe-se que:

    1. Ana não estava vestida de pirata.
    2. Quem estava de super-herói não é Bruno.
    3. Caio não estava de palhaço nem de super-herói.

    Descubra a fantasia de cada um usando **eliminação lógica**.

    Dica: monte uma tabela com as pessoas nas linhas e as fantasias nas
    colunas, marcando "impossível" a cada pista, até sobrar só uma opção por
    pessoa.

    **Resolução guiada:** pela pista 3, Caio só pode estar de **pirata**
    (já que palhaço e super-herói estão eliminados para ele). Pela pista 1,
    Ana não é pirata — como Caio já é pirata, isso é consistente, e Ana só
    pode ser **super-herói** ou **palhaço**. Pela pista 2, quem é
    super-herói não é Bruno — logo Bruno não pode ser super-herói, sobrando
    **palhaço** para Bruno. Por eliminação, Ana fica com **super-herói**.

!!! tip "Por que isso importa?"
    Esse tipo de quebra-cabeça de "eliminação" é resolvido formalmente com
    **lógica proposicional** — exatamente o que vem na próxima aula. Se você
    resolveu o desafio "no olho", parabéns: você já está pensando como a
    matemática que vamos formalizar em [Fundamentos de lógica](03-aula.md).

## 📝 Antes da próxima aula

!!! check "Checklist de saída"
    - [ ] Diagnóstico de onboarding 100% marcado (ou dúvida já reportada ao
      professor).
    - [ ] Ambiente Python + VS Code + Git testado e funcionando.
    - [ ] Nenhuma dúvida pendente sobre o cronograma ou a avaliação.

## 📚 Referências

**Sobre evasão e permanência estudantil (contexto institucional)**

- SEMESP. *Mapa do Ensino Superior no Brasil* — indicadores de evasão e
  permanência no ensino superior privado.
- ABMES. *Retenção e permanência estudantil no ensino superior* — práticas
  de acompanhamento e busca ativa.

**Ferramentas (revisão rápida)**

- Guia de instalação da turma: [🧰 Ferramentas](../ferramentas.md).
- Python — instalação oficial: <https://www.python.org/downloads/>
- Git — instalação oficial: <https://git-scm.com/downloads>

**🎥 Vídeos**

- Canal **Curso em Vídeo** (Gustavo Guanabara) — série de Lógica de
  Programação, ótima para quem quer reforçar o "porquê" por trás do
  raciocínio lógico antes da próxima aula:
  <https://www.youtube.com/results?search_query=curso+em+v%C3%ADdeo+l%C3%B3gica+de+programa%C3%A7%C3%A3o>
- Busca geral por tutoriais de configuração de ambiente Python + Git para
  iniciantes:
  <https://www.youtube.com/results?search_query=instalar+python+git+vscode+iniciantes>

!!! tip "Próxima Parada 🚏"
    Com o ambiente e as dúvidas resolvidos, começamos de verdade com
    **[Fundamentos de lógica](03-aula.md)**.
