# 🚀 Lista 03 — Funções

!!! abstract "Missão"
    Explorar funções, suas classificações e composição, com base na
    **[Aula 03](../aulas/03-aula.md)**, implementando em **Python**.

## 🎯 Objetivo

Distinguir injetora, sobrejetora e bijetora; calcular imagem e composição de
funções sobre domínios finitos.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista03`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista03.git
   cd una-mca-lista03
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 03"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Imagem e classificação"
    Para $f(x)=2x$ sobre $\{0,1,2,3\}$ (contradomínio $\{0,\dots,6\}$), calcule a
    imagem e diga se é injetora e/ou sobrejetora.

??? abstract "Exercício 2 — Exemplos"
    Escreva uma função sobrejetora **não** injetora e outra injetora **não**
    sobrejetora; comprove com código.

??? abstract "Exercício 3 — Composição"
    Com $f(x)=x+2$ e $g(x)=3x$, implemente $g \circ f$ e $f \circ g$ e mostre que
    diferem.

??? abstract "Exercício 4 — Bijeção"
    Implemente `eh_bijetora(f, dominio, contradominio)` e teste com um caso
    verdadeiro e um falso.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista03/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista03`.
    - [ ] Um arquivo por exercício.
    - [ ] Códigos rodam sem erro.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
