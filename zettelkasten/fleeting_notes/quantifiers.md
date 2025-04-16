# ∀ Quantificadores Lógicos

Este documento apresenta os principais **quantificadores lógicos**, usados para expressar proposições sobre conjuntos, variáveis e generalizações em lógica matemática.

---

## 🧠 O que são quantificadores?

Quantificadores permitem expressar afirmações sobre **todos os elementos** ou **algum elemento** de um domínio (ex: conjunto de números, pessoas, objetos...).

---

## 🔁 Tipos de Quantificadores

### 1. Quantificador Universal (`∀`)

> "Para todo x, P(x)"

Símbolo: `∀x P(x)`

Significado: A proposição `P(x)` é verdadeira **para todos os valores** de `x` no domínio.

**Exemplo:**
> ∀x ∈ ℝ, x² ≥ 0  
> "Todo número real ao quadrado é maior ou igual a zero."

---

### 2. Quantificador Existencial (`∃`)

> "Existe ao menos um x tal que P(x)"

Símbolo: `∃x P(x)`

Significado: Existe **pelo menos um valor de x** no domínio tal que `P(x)` é verdadeira.

**Exemplo:**
> ∃x ∈ ℕ, x² = 9  
> "Existe um número natural cujo quadrado é 9."

---

## 📊 Tabela Comparativa

| Propriedade               | `∀x P(x)`                  | `∃x P(x)`                    |
|---------------------------|----------------------------|------------------------------|
| Lida como                 | "Para todo x..."           | "Existe x tal que..."        |
| Verdade exige             | Todos satisfazem `P(x)`    | Ao menos um satisfaz `P(x)`  |
| Negação                   | `¬∀x P(x)` ≡ `∃x ¬P(x)`     | `¬∃x P(x)` ≡ `∀x ¬P(x)`       |
| Tipo                      | Generalização              | Existência                   |

---

## ❗ Negação de Quantificadores

### Regra de negação:

| Original          | Negação Equivalente          |
|------------------|------------------------------|
| `∀x P(x)`        | `∃x ¬P(x)`                   |
| `∃x P(x)`        | `∀x ¬P(x)`                   |

> 📌 **Negar uma afirmação universal resulta em uma afirmação existencial com a negação do predicado — e vice-versa.**

---

## 🧩 Exemplo de Tradução

Frase:  
> "Nem todos os estudantes passaram na prova."

Tradução:
> ¬∀x (Estudante(x) → Passou(x))  
Equivalente:
> ∃x (Estudante(x) ∧ ¬Passou(x))

---

## 💬 Quantificadores em Cadeia

É possível usar múltiplos quantificadores em sequência:

```text
∀x ∈ ℝ, ∃y ∈ ℝ tal que y² = x
```

> "Para todo número real x, existe um número real y tal que y² = x"  
⚠️ FALSO — pois `y² = -1` não tem solução real

---

## 🔁 Ordem Importa!

```text
∀x ∃y P(x, y) ≠ ∃y ∀x P(x, y)
```

> A troca da ordem pode mudar completamente o significado da proposição!

---

## 📚 Referências

- [Discrete Math - Quantifiers](https://math.libretexts.org/Bookshelves/Discrete_Mathematics)
- [Symbolic Logic (forall, exists)](https://plato.stanford.edu/entries/logic-classical/#SymbLogi)
- [Livro: Rosen - Discrete Mathematics](https://www.mheducation.com/)

---

Este arquivo faz parte da seção [`mathematics/logic`](./), com foco em representação formal e precisão semântica.
