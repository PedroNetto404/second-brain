# 📐 Métodos de Prova em Lógica

Este documento apresenta as principais **estratégias de demonstração matemática**, usadas para provar afirmações baseadas em proposições e quantificadores.

---

## ✅ O que é uma prova?

Uma **prova** é uma sequência finita e lógica de argumentos que mostra, de forma irrefutável, que uma proposição é verdadeira, partindo de axiomas e/ou hipóteses.

---

## 📦 1. Prova Direta

Consiste em assumir a hipótese e, por meio de deduções lógicas, chegar à conclusão desejada.

### Exemplo:

> Provar: Se `n` é par, então `n²` é par.

**Prova:**  
Se `n` é par, então `n = 2k` para algum `k ∈ ℤ`.  
Logo, `n² = (2k)² = 4k² = 2(2k²)` → é múltiplo de 2 → **par**.

✅ Q.E.D. (*quod erat demonstrandum*)

---

## 🔄 2. Prova por Contrapositiva

Em vez de provar `p → q`, provamos `¬q → ¬p`, que é logicamente equivalente.

### Exemplo:

> Provar: Se `n²` é ímpar, então `n` é ímpar.

**Contrapositiva:**  
Se `n` é par, então `n²` é par.  
(Demonstramos isso na prova direta anterior.)

✔️ Logo, a proposição original também é verdadeira.

---

## ❌ 3. Prova por Contradição

Assuma que a proposição **é falsa**, e mostre que isso leva a um absurdo.

### Exemplo:

> Provar: √2 é irracional.

**Suposição contrária:**  
Suponha √2 = a/b, com `a, b ∈ ℤ` e `mdc(a, b) = 1`.  
⇒ `2 = a²/b² ⇒ a² = 2b²`  
⇒ `a²` par ⇒ `a` par ⇒ `a = 2k`  
⇒ Substituindo: `4k² = 2b²` ⇒ `b² = 2k²` ⇒ `b²` par ⇒ `b` par  
⇒ `a` e `b` pares ⇒ mdc(a, b) ≥ 2 → contradição.

✅ Conclusão: √2 não pode ser racional.

---

## 🔁 4. Prova por Indução Matemática

Usada para proposições envolvendo números naturais.

### Estrutura:

1. **Base**: Prove que a afirmação vale para `n = 1`
2. **Hipótese de Indução**: Suponha que vale para `n = k`
3. **Passo indutivo**: Mostre que vale para `n = k + 1`

### Exemplo:

> Provar: `1 + 2 + 3 + ... + n = n(n+1)/2`

**Base:**  
`n = 1`: `1 = 1(1+1)/2 = 1` ✔️

**Hipótese:**  
Assuma que vale para `n = k`:  
`1 + 2 + ... + k = k(k+1)/2`

**Passo:**  
Para `n = k + 1`:  
`S = k(k+1)/2 + (k+1) = (k+1)(k+2)/2` ✔️

✅ A fórmula é verdadeira ∀n ∈ ℕ

---

## 🧪 Outros Métodos

- **Exaustão**: Testar todos os casos possíveis (viável só em domínios finitos)
- **Existência/Contraconstrução**: Exibir um contraexemplo ou um exemplo explícito
- **Equivalência lógica**: Demonstrar que duas expressões são logicamente equivalentes

---

## 🔧 Notações Comuns

| Símbolo   | Significado             |
|-----------|--------------------------|
| `∴`       | Portanto                 |
| `⇒`       | Implica                  |
| `⇔`       | Se e somente se (equivalente) |
| `Q.E.D.`  | Final de prova           |

---

## 📚 Referências

- [Livro: Rosen - Discrete Mathematics](https://www.mheducation.com/)
- [How to Write a Proof - MathWorld](https://mathworld.wolfram.com/Proof.html)
- [Types of Proofs - Brilliant](https://brilliant.org/wiki/proof-techniques/)

---

Este documento faz parte da seção [`mathematics/logic`](./), voltada à formalização de raciocínios com precisão e clareza matemática.
