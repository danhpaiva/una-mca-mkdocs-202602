# 🚀 Lista 05 — Equivalências e argumentos

!!! abstract "Missão"
    Provar equivalências lógicas e validar argumentos, com base na
    **[Aula 05](../aulas/05-aula.md)**, usando **Python**.

## 🎯 Objetivo

Demonstrar equivalências por tabela-verdade, aplicar leis (De Morgan,
contrapositiva) e testar a validade de argumentos.

## 🗺️ Passo a passo da entrega

1. **Crie um repositório público** chamado **`una-mca-lista05`**.
2. **Clone**:
   ```bash
   git clone https://github.com/SEU_USUARIO/una-mca-lista05.git
   cd una-mca-lista05
   ```
3. Resolva os exercícios (um `.py` por exercício).
4. **Commit + push**:
   ```bash
   git add .
   git commit -m "feat: resolve exercícios da lista 05"
   git push origin main
   ```
5. **Entregue o link** no **Google Classroom**.

!!! danger "Repositório privado = entrega não avaliada"
    Confirme que o repositório está **público**.

## 📝 Exercícios

??? abstract "Exercício 1 — De Morgan"
    Prove por código (comparando tabelas-verdade) que
    $\neg(p \vee q) \equiv \neg p \wedge \neg q$.

??? abstract "Exercício 2 — Contrapositiva"
    Reescreva "Se não estudo, então não passo" na forma contrapositiva e verifique
    a equivalência em código.

??? abstract "Exercício 3 — Validade"
    Teste se o argumento (premissas $p \to q$, $\neg p$; conclusão $\neg q$) é
    válido, procurando um contraexemplo.

??? abstract "Exercício 4 — Validador genérico"
    Implemente `eh_valido(premissas, conclusao, n_vars)`, com premissas como lista
    de `lambda`s, e teste com **Modus Tollens**.

## 📁 Estrutura de pastas sugerida

```text
una-mca-lista05/
├── README.md
├── exercicio1.py
├── exercicio2.py
├── exercicio3.py
└── exercicio4.py
```

## ✅ Checklist de qualidade

!!! check "Antes de entregar, confira"
    - [ ] Repositório **público** `una-mca-lista05`.
    - [ ] Um arquivo por exercício.
    - [ ] Cada prova/validação imprime a conclusão claramente.
    - [ ] `README.md` documenta a lista.
    - [ ] Commit + `push` concluídos.
    - [ ] Link entregue no **Google Classroom**.
