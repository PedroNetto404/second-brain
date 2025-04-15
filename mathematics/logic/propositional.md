# 🔢 Lógica Proposicional

Este documento apresenta os fundamentos da **lógica proposicional**, usada para formalizar sentenças e raciocínios lógicos com base em proposições verdadeiras ou falsas.

---

## 🧠 O que é uma Proposição?

Uma **proposição** é uma sentença declarativa que pode ser **verdadeira (V)** ou **falsa (F)**, mas nunca ambos ao mesmo tempo.

✅ Exemplos de proposições:
- "2 + 2 = 4"
- "A Terra gira em torno do Sol"

❌ Não são proposições:
- "Como você está?" (pergunta)
- "X + 2 = 4" (sem valor lógico definido)

---

## 🔁 Operadores Lógicos

| Operador       | Símbolo     | Nome                       | Exemplo                    |
|----------------|-------------|----------------------------|----------------------------|
| Negação        | ¬p ou ~p    | **Não**                    | ¬p: "Não é verdade que p"  |
| Conjunção      | p ∧ q       | **E** (AND)                | "p e q são verdadeiros"    |
| Disjunção      | p ∨ q       | **Ou** (OR inclusivo)      | "p ou q é verdadeiro"      |
| Condicional    | p → q       | **Se...então**             | "Se p, então q"            |
| Bicondicional  | p ↔ q       | **Se e somente se**        | "p se e somente se q"      |

---

## 📊 Tabela-Verdade

### Exemplo: p ∧ q

| p | q | p ∧ q |
|---|---|--------|
| V | V | V      |
| V | F | F      |
| F | V | F      |
| F | F | F      |

### Exemplo: p → q

| p | q | p → q |
|---|---|--------|
| V | V | V      |
| V | F | F      |
| F | V | V      |
| F | F | V      |

> 🧠 **Condicional só é falsa quando o antecedente é verdadeiro e o consequente é falso.**

---

## 🔄 Equivalências Lógicas Importantes

| Expressão Original       | Equivalente Lógica               |
|--------------------------|----------------------------------|
| ¬(p ∧ q)                 | ¬p ∨ ¬q   (De Morgan)            |
| ¬(p ∨ q)                 | ¬p ∧ ¬q   (De Morgan)            |
| p → q                    | ¬p ∨ q                           |
| p ↔ q                    | (p ∧ q) ∨ (¬p ∧ ¬q)              |
| ¬(p → q)                 | p ∧ ¬q                           |

---

## 🔍 Tautologias, Contradições e Contingências

- **Tautologia**: Sempre verdadeira (ex: p ∨ ¬p)
- **Contradição**: Sempre falsa (ex: p ∧ ¬p)
- **Contingência**: Pode ser V ou F, dependendo dos valores

---

## 🧪 Exercício Rápido

Verifique se a equivalência é válida:
> (p → q) ≡ (¬p ∨ q)

→ Faça a tabela-verdade para ambas expressões e compare os resultados.

---

## 📚 Referências

- [Rosen, Discrete Mathematics and Its Applications](https://www.mheducation.com/)
- [Introduction to Logic - Stanford Encyclopedia of Philosophy](https://plato.stanford.edu/entries/logic-classical/)
- [Lógica Proposicional - Khan Academy](https://pt.khanacademy.org/computing/computer-science/cryptography/logic/a/logic-notation)

---

Este conteúdo faz parte da seção [`mathematics/logic`](./), voltada à formalização de raciocínios, provas e sistemas simbólicos.
