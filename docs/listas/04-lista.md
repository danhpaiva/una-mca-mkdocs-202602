# 🚀 Lista 04 — Lógica proposicional

!!! abstract "Missão"
    Construir tabelas-verdade e classificar fórmulas, com base na
    **[Aula 04](../aulas/04-aula.md)**, usando **Python**.

## 🎯 Objetivo

Avaliar conectivos lógicos, gerar tabelas-verdade automaticamente e identificar
tautologias, contradições e contingências.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista04`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista04.git
   cd una-mca-lista04
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 04"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — Tabela-verdade"
    Imprima a tabela-verdade completa de $\neg(p \wedge q)$.

??? abstract "Exercício 2 — Tradução"
    Modele "Se estudo e durmo bem, então passo" com funções lógicas e mostre uma
    linha em que a fórmula é falsa.

??? abstract "Exercício 3 — Classificação"
    Classifique como tautologia/contradição/contingência: (a) $(p \to q)\vee p$;
    (b) $p \wedge \neg p$; (c) $p \to (p \vee q)$.

??? abstract "Exercício 4 — Gerador"
    Escreva uma função que imprima a tabela-verdade de qualquer fórmula com 3
    variáveis passada como `lambda` (use `itertools.product`).

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista04/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista04`.
    - [ ] Um arquivo por exercício.
    - [ ] Tabelas-verdade impressas de forma legível.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
