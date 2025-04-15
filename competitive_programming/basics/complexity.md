# ⏱️ Complexidade Computacional

Este documento apresenta os fundamentos de **complexidade de tempo e espaço**, essenciais para estimar a viabilidade de soluções em programação competitiva.

---

## 🧠 1. O que é complexidade?

A complexidade mede o **custo computacional** de um algoritmo em função do tamanho da entrada `n`.

- **Complexidade de tempo**: quantas operações são realizadas
- **Complexidade de espaço**: quanta memória extra é utilizada

---

## 🅾️ 2. Notação O-grande (`O(n)`)

### Crescimento assintótico

| Notação         | Nome                     | Exemplo típico                      |
|-----------------|--------------------------|--------------------------------------|
| `O(1)`          | Constante                | Acesso direto em vetor               |
| `O(log n)`      | Logarítmica              | Busca binária                        |
| `O(n)`          | Linear                   | Percorrer vetor                     |
| `O(n log n)`    | Linearítmica             | Mergesort, sort()                   |
| `O(n²)`         | Quadrática               | Duplo for aninhado                   |
| `O(2ⁿ)`         | Exponencial              | Backtracking bruto                   |
| `O(n!)`         | Fatorial                 | Permutações completas                |

---

## 📐 3. Estimando Tempo com `n`

**Dica geral**:
- `10⁸` operações ≈ 1 segundo de CPU

| Valor máximo de `n` | Complexidade viável           |
|---------------------|-------------------------------|
| ≤ 10                | `O(n!)`, `O(2ⁿ)`              |
| ≤ 100               | `O(n³)`, `O(n² log n)`        |
| ≤ 1.000             | `O(n²)`                       |
| ≤ 10⁵               | `O(n log n)`                  |
| ≤ 10⁶ – 10⁷         | `O(n)`                        |
| ≥ 10⁸               | Apenas `O(1)` ou leitura direta|

---

## 📊 4. Complexidade de Espaço

Considere os limites de memória (ex: 256MB):

```cpp
int arr[1000000]; // ocupa ~8MB (1e6 * 8 bytes para int64_t)
bool vis[1000][1000]; // ~1MB
```

Dica: `1e5` inteiros ocupam ~800KB

---

## 🔄 5. Pior caso vs melhor caso

**Maratonas exigem análise do pior caso.**

Exemplo:

```cpp
for (int i = 1; i <= n; i *= 2) // O(log n)
for (int j = 1; j <= n; j++)   // O(n)
```

Complexidade total: `O(n log n)`

---

## 📚 6. Problemas Típicos por Complexidade

| Complexidade | Problemas Típicos                          |
|--------------|---------------------------------------------|
| `O(1)`       | Operações matemáticas diretas              |
| `O(log n)`   | Busca binária, exponenciação binária       |
| `O(n)`       | Contagem, prefix sums                      |
| `O(n log n)` | Ordenação, mergesort, divisão e conquista  |
| `O(n²)`      | Floyd-Warshall, brute-force leve           |
| `O(2ⁿ)`      | Backtracking, subconjuntos                 |

---

## 🛠️ 7. Ferramentas de Análise

- [Big O Cheat Sheet](https://www.bigocheatsheet.com/)
- [CP Algorithms - Complexity](https://cp-algorithms.com/)
- [Visualizer - Time Complexity](https://www.cs.usfca.edu/~galles/visualization/Algorithms.html)

---

Este documento faz parte da seção [`competitive_programming/basics`](./), e ajuda a escolher a abordagem certa com base nas restrições de tempo e memória.
# ⏱️ Complexidade Computacional

Este documento apresenta os fundamentos de **complexidade de tempo e espaço**, essenciais para estimar a viabilidade de soluções em programação competitiva.

---

## 🧠 1. O que é complexidade?

A complexidade mede o **custo computacional** de um algoritmo em função do tamanho da entrada `n`.

- **Complexidade de tempo**: quantas operações são realizadas
- **Complexidade de espaço**: quanta memória extra é utilizada

---

## 🅾️ 2. Notação O-grande (`O(n)`)

### Crescimento assintótico

| Notação         | Nome                     | Exemplo típico                      |
|-----------------|--------------------------|--------------------------------------|
| `O(1)`          | Constante                | Acesso direto em vetor               |
| `O(log n)`      | Logarítmica              | Busca binária                        |
| `O(n)`          | Linear                   | Percorrer vetor                     |
| `O(n log n)`    | Linearítmica             | Mergesort, sort()                   |
| `O(n²)`         | Quadrática               | Duplo for aninhado                   |
| `O(2ⁿ)`         | Exponencial              | Backtracking bruto                   |
| `O(n!)`         | Fatorial                 | Permutações completas                |

---

## 📐 3. Estimando Tempo com `n`

**Dica geral**:
- `10⁸` operações ≈ 1 segundo de CPU

| Valor máximo de `n` | Complexidade viável           |
|---------------------|-------------------------------|
| ≤ 10                | `O(n!)`, `O(2ⁿ)`              |
| ≤ 100               | `O(n³)`, `O(n² log n)`        |
| ≤ 1.000             | `O(n²)`                       |
| ≤ 10⁵               | `O(n log n)`                  |
| ≤ 10⁶ – 10⁷         | `O(n)`                        |
| ≥ 10⁸               | Apenas `O(1)` ou leitura direta|

---

## 📊 4. Complexidade de Espaço

Considere os limites de memória (ex: 256MB):

```cpp
int arr[1000000]; // ocupa ~8MB (1e6 * 8 bytes para int64_t)
bool vis[1000][1000]; // ~1MB
```

Dica: `1e5` inteiros ocupam ~800KB

---

## 🔄 5. Pior caso vs melhor caso

**Maratonas exigem análise do pior caso.**

Exemplo:

```cpp
for (int i = 1; i <= n; i *= 2) // O(log n)
for (int j = 1; j <= n; j++)   // O(n)
```

Complexidade total: `O(n log n)`

---

## 📚 6. Problemas Típicos por Complexidade

| Complexidade | Problemas Típicos                          |
|--------------|---------------------------------------------|
| `O(1)`       | Operações matemáticas diretas              |
| `O(log n)`   | Busca binária, exponenciação binária       |
| `O(n)`       | Contagem, prefix sums                      |
| `O(n log n)` | Ordenação, mergesort, divisão e conquista  |
| `O(n²)`      | Floyd-Warshall, brute-force leve           |
| `O(2ⁿ)`      | Backtracking, subconjuntos                 |

---

## 🛠️ 7. Ferramentas de Análise

- [Big O Cheat Sheet](https://www.bigocheatsheet.com/)
- [CP Algorithms - Complexity](https://cp-algorithms.com/)
- [Visualizer - Time Complexity](https://www.cs.usfca.edu/~galles/visualization/Algorithms.html)

---

Este documento faz parte da seção [`competitive_programming/basics`](./), e ajuda a escolher a abordagem certa com base nas restrições de tempo e memória.
