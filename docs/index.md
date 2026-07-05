# 🧮 Matemática Computacional Aplicada

Bem-vindo(a)! Aqui você encontra todo o material de apoio, o cronograma e as
orientações de entrega da nossa disciplina.

!!! info "Objetivo da Disciplina"
    Desenvolver o **raciocínio matemático discreto** necessário à Computação:
    conjuntos, relações e funções; lógica proposicional e álgebra booleana;
    contagem e combinatória; estruturas como matrizes, grafos e árvores; e
    indução/recorrência. A meta é que você aprenda a **modelar problemas
    computacionais** e a **justificar formalmente** algoritmos e estruturas de
    dados.

## 🎯 O que você vai aprender

=== "🧠 Fundamentos"
    - Operar com **conjuntos, relações e funções**.
    - Escrever e avaliar **proposições lógicas** com tabelas-verdade.
    - Aplicar **equivalências lógicas** na simplificação de raciocínios.

=== "⚙️ Estruturas & Contagem"
    - Simplificar expressões de **álgebra booleana** e projetar circuitos.
    - Resolver problemas com **princípios de contagem e combinatória**.
    - Modelar dados com **matrizes, grafos e árvores**.

=== "🔁 Prova & Aplicação"
    - Provar propriedades por **indução matemática**.
    - Definir e resolver **recorrências**.
    - Conectar tudo a **algoritmos e estruturas de dados**.

## 🗓️ Cronograma

| Aula | Assunto | Entrega |
| :--- | :--- | :--- |
| [01](aulas/01-aula.md) | Conjuntos: fundamentos e operações | [Lista 01](listas/01-lista.md) |
| [02](aulas/02-aula.md) | Relações | [Lista 02](listas/02-lista.md) |
| [03](aulas/03-aula.md) | Funções | [Lista 03](listas/03-lista.md) |
| [04](aulas/04-aula.md) | Lógica proposicional e tabelas-verdade | [Lista 04](listas/04-lista.md) |
| [05](aulas/05-aula.md) | Equivalências lógicas e argumentos | [Lista 05](listas/05-lista.md) |
| [06](aulas/06-aula.md) | Álgebra booleana | [Lista 06](listas/06-lista.md) |
| [07](aulas/07-aula.md) | Circuitos digitais e aplicações | [Lista 07](listas/07-lista.md) |
| [08](aulas/08-aula.md) | Princípios de contagem | [Lista 08](listas/08-lista.md) |
| [09](aulas/09-aula.md) | Combinatória | [Lista 09](listas/09-lista.md) |
| [10](aulas/10-aula.md) | Matrizes | [Lista 10](listas/10-lista.md) |
| [11](aulas/11-aula.md) | Grafos e árvores | [Lista 11](listas/11-lista.md) |
| [12](aulas/12-aula.md) | Indução matemática e recorrência | [Lista 12](listas/12-lista.md) |

## 🛠️ Ferramentas

=== "🐍 Python"
    Usaremos **Python** para transformar teoria em código. Um gostinho:

    ```python
    # Conjuntos são nativos em Python
    A = {1, 2, 3, 4}
    B = {3, 4, 5, 6}

    print("União:", A | B)          # {1, 2, 3, 4, 5, 6}
    print("Interseção:", A & B)     # {3, 4}
    print("Diferença:", A - B)      # {1, 2}
    ```

=== "📦 Ambiente"
    - **Python 3.10+** (recomendado 3.12).
    - Editor: **VS Code** ou similar.
    - **Git + GitHub** para versionar e entregar as listas.

    Veja o passo a passo em [🧰 Ferramentas](ferramentas.md).

## 💡 Dicas de estudo

!!! tip "Como aproveitar melhor"
    - Refaça os exemplos das aulas **rodando o código**, não só lendo.
    - Resolva as listas **logo após** a aula correspondente.
    - Sempre que possível, **prove ou teste** o resultado (com exemplos e
      contraexemplos).

??? abstract "Como as entregas funcionam?"
    Cada aula tem uma **Lista** no formato *Missão*. Você cria um repositório
    público `una-mca-listaNN`, sobe seu código e entrega o **link** no Google
    Classroom. O passo a passo completo está em cada lista.

!!! danger "Atenção com Prazos"
    O Google Classroom fecha automaticamente para entregas atrasadas. Comece cedo!
