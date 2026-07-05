# 🚀 Lista 08 — Contagem

!!! abstract "Missão"
    Aplicar os princípios de contagem da **[Aula 08](../aulas/08-aula.md)**
    (aditivo, multiplicativo, inclusão-exclusão, casa dos pombos) em **Python**.

## 🎯 Objetivo

Contar possibilidades corretamente, decidindo entre somar e multiplicar, e usar
inclusão-exclusão em conjuntos que se sobrepõem.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista08`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista08.git
   cd una-mca-lista08
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 08"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Placas"
    Calcule quantas placas no formato **3 letras + 4 dígitos** existem (A–Z, 0–9).

??? abstract "Exercício 2 — Inclusão-exclusão"
    20 fazem estágio, 12 são monitores, 5 fazem os dois. Calcule quantos fazem
    pelo menos uma e exatamente uma atividade (com conjuntos em Python).

??? abstract "Exercício 3 — Casa dos pombos"
    Escreva um programa que, dado um grupo de $n$ pessoas e $k$ "casas", diga se é
    **garantido** que duas caiam na mesma casa.

??? abstract "Exercício 4 — Contador de senhas"
    Implemente `conta_senhas(tam, alfabeto)` e confirme, para casos pequenos,
    contra `len(list(itertools.product(...)))`.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista08/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista08`.
    - [ ] Um arquivo por exercício.
    - [ ] Cada resposta numérica é impressa e explicada.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
