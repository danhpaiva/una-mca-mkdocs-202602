# 01. Introdução e apresentação da UC

!!! info "Nesta aula"
    - O que é a UC (Unidade Curricular) e por que ela existe no seu curso.
    - Como o semestre está organizado: aulas, atividades e atividade em grupo.
    - Ferramentas que vamos usar.
    - Como tirar dúvidas e onde entregar as atividades.

## 🧭 Por que "Matemática Computacional Aplicada"?

Todo sistema que você vai construir na sua carreira — de um app simples a um
motor de busca — é, por baixo dos panos, **lógica formal** e **estruturas
discretas** rodando em silício. Esta UC existe para dar a você o vocabulário e
o raciocínio que sustentam:

- Por que um `if` funciona do jeito que funciona (**lógica proposicional**).
- Por que um processador consegue somar números (**álgebra booleana e
  circuitos digitais**).
- Como redes, mapas e organogramas viram código (**grafos e árvores**).
- Como tudo isso se conecta às **estruturas de dados e algoritmos** que você
  verá nas próximas disciplinas.

!!! note "Você já usa isso, mesmo sem saber"
    Toda vez que você escreve `if a and b:` em Python, está avaliando uma
    **proposição composta**. Toda vez que usa `&`, `|` ou `~` em bits, está
    fazendo **álgebra booleana**. Esta UC só coloca nome e rigor no que você
    já intui.

!!! example "Onde cada assunto aparece fora da sala de aula"
    | Assunto da UC | Onde aparece na prática |
    | :--- | :--- |
    | Lógica proposicional | Regras de validação de formulário (`if idade >= 18 and cpf_valido:`) |
    | Álgebra booleana | Filtros de banco de dados (`WHERE ativo = true AND saldo > 0`) |
    | Circuitos digitais | O processador do seu celular, literalmente feito de portas lógicas |
    | Grafos | Rotas do Google Maps, feed de recomendação, rede de amigos |
    | Árvores | Pastas do seu computador, índice de um banco de dados, o DOM de uma página web |

    Nenhum desses exemplos é abstrato: cada um é um sistema real que você já
    usou esta semana.

## 🗓️ Como o semestre está organizado

Este trilho segue o calendário real do semestre — incluindo aulas de busca
ativa, atividades práticas, orientação de trabalho e avaliações. A tabela
completa está na **[página inicial desta trilha](index.md)**.

=== "📚 Conteúdo"
    - **Lógica proposicional** — fundamentos, conectivos, tabelas-verdade.
    - **Álgebra booleana** — axiomas, simplificação, mapas de Karnaugh.
    - **Circuitos digitais** — portas lógicas, somadores.
    - **Grafos e árvores** — modelagem, representação, percursos.
    - **Fechamento** — como tudo isso vira estrutura de dados e algoritmo.

=== "🛠️ Prática"
    - Aulas de **atividades/prática de aplicação** (duas ao longo do
      semestre) para consolidar o conteúdo com exercícios guiados.
    - Duas aulas de **Busca Ativa**, dedicadas a identificar e reengajar
      quem está atrasado ou ausente.

=== "✅ Avaliação"
    - **Atividade avaliativa em grupo**, feita em sala.

!!! note "Avaliações A1 e A3"
    As avaliações individuais (A1) e a atividade aplicada (A3) são tratadas
    em material didático separado, fora desta trilha semanal.

!!! danger "Placeholders para o professor"
    Datas exatas, peso da avaliação em grupo e regras específicas de entrega
    (Google Classroom, formato de arquivo, etc.) devem ser preenchidos pelo
    professor responsável antes da primeira aula. Os textos desta trilha
    trazem uma estrutura pronta, mas a logística final é institucional.

## 🎯 O que você deve conseguir fazer ao final

- Construir e interpretar **tabelas-verdade**.
- Simplificar expressões de **álgebra booleana** e projetar circuitos simples.
- Modelar problemas com **grafos e árvores**.
- Explicar, com suas palavras, **por que** essas ferramentas aparecem em
  estruturas de dados e algoritmos do dia a dia.

## 🛠️ Ferramentas

Vamos programar em **Python** para transformar teoria em código verificável.

```python
# Um "if" nada mais é que avaliar uma proposição composta
estudou = True
dormiu_bem = True

if estudou and dormiu_bem:
    print("Passou!")
```

!!! example "Mais um exemplo: várias condições encadeadas"
    ```python
    idade = 20
    tem_ingresso = True
    acompanhado = False

    # "pode entrar" se (tem ingresso) e (é maior de idade OU está acompanhado)
    pode_entrar = tem_ingresso and (idade >= 18 or acompanhado)
    print(pode_entrar)  # True
    ```
    Repare que a estrutura é **exatamente** a de uma fórmula lógica com
    parênteses — o mesmo tipo de expressão que vamos formalizar na
    [Aula 04](04-aula.md).

Veja o passo a passo de instalação em **[🧰 Ferramentas](../ferramentas.md)**.
Você vai precisar de:

- **Python 3.10+**
- **VS Code** (ou editor equivalente)
- **Git + GitHub**, para versionar e entregar atividades

## 💬 Como tirar dúvidas

!!! tip "Antes de perguntar, tente"
    1. Reler a seção da aula relacionada à sua dúvida.
    2. Rodar o código de exemplo você mesmo, alterando os valores.
    3. Formular a dúvida como uma pergunta específica ("por que X não dá Y?"),
       não genérica ("não entendi nada").

Dúvidas de conteúdo: procure o professor nos horários de atendimento ou pelo
canal oficial da turma. Dúvidas sobre entregas: confira sempre a página da
aula correspondente antes de perguntar — o passo a passo costuma estar lá.

## 📝 Antes da próxima aula

??? abstract "Checklist de preparação"
    - [ ] Instalar Python, VS Code e Git (veja [Ferramentas](../ferramentas.md)).
    - [ ] Criar (ou confirmar) uma conta no GitHub.
    - [ ] Rodar o exemplo de `if` acima e testar com `estudou = False`.
    - [ ] Ler a [visão geral do cronograma](index.md) desta trilha.

## 📚 Referências

**Livros (visão geral da disciplina)**

- ROSEN, K. H. *Matemática Discreta e suas Aplicações*. 7. ed. Porto Alegre:
  AMGH/McGraw-Hill — o livro-texto de referência do curso, cobre todos os
  temas que veremos.
- GERSTING, J. L. *Fundamentos Matemáticos para a Ciência da Computação*.
  7. ed. Rio de Janeiro: LTC — abordagem mais próxima da Computação.
- SCHEINERMAN, E. R. *Matemática Discreta: uma introdução*. São Paulo:
  Cengage.

**Documentação e prática (Python)**

- Python — documentação oficial (tutorial): <https://docs.python.org/3/tutorial/>
- Guia de instalação da turma: [🧰 Ferramentas](../ferramentas.md)

**🎥 Vídeos**

- Canal **Curso em Vídeo** (Gustavo Guanabara) — série de Lógica de
  Programação, excelente para quem está começando do zero:
  <https://www.youtube.com/results?search_query=curso+em+v%C3%ADdeo+l%C3%B3gica+de+programa%C3%A7%C3%A3o>
- CS50 (Harvard) — aula introdutória sobre como computadores representam e
  processam informação (legendado em português em algumas plataformas):
  <https://www.youtube.com/results?search_query=cs50+introduction+binary+logic>

!!! tip "Próxima Parada 🚏"
    Nosso próximo encontro é a **[Busca Ativa — Início de Semestre](02-aula.md)**,
    para acertar ferramentas e dúvidas de ementa. Depois disso, começamos de
    verdade com **[Fundamentos de lógica](03-aula.md)**.
