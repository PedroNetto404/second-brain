# 🎲 Combinatória para Competições

A combinatória estuda contagens, arranjos e seleções de elementos. Em programação competitiva, ela aparece em problemas de:

- contagem de caminhos
- combinações de escolhas
- probabilidades
- permutações com restrições

---

## 🧠 1. Fatorial

```cpp
int fact(int n) {
    int res = 1;
    for (int i = 2; i <= n; i++)
        res *= i;
    return res;
}
```

⚠️ Para `n ≥ 20`, cuidado com overflow. Use `int64_t` ou módulo.

---

## 🔁 2. Permutação

| Fórmula             | Interpretação                         |
|---------------------|----------------------------------------|
| `P(n, r) = n! / (n - r)!` | Número de maneiras de **escolher e ordenar** `r` elementos de `n` |

```cpp
int perm(int n, int r) {
    return fact(n) / fact(n - r);
}
```

---

## 🔄 3. Combinação

| Fórmula             | Interpretação                         |
|---------------------|----------------------------------------|
| `C(n, r) = n! / (r! (n - r)!)` | Número de maneiras de **escolher** `r` elementos de `n`, **sem ordem** |

```cpp
int comb(int n, int r) {
    return fact(n) / (fact(r) * fact(n - r));
}
```

---

## ⚡ 4. Pré-cálculo com Módulo

Usado para combinar eficiência e aritmética modular.

```cpp
const int MOD = 1e9 + 7;
const int MAXN = 1e6 + 5;

int fact[MAXN], inv[MAXN];

int binpow(int a, int b) {
    int res = 1;
    while (b) {
        if (b & 1) res = res * a % MOD;
        a = a * a % MOD;
        b >>= 1;
    }
    return res;
}

void precompute() {
    fact[0] = inv[0] = 1;
    for (int i = 1; i < MAXN; i++) {
        fact[i] = fact[i - 1] * i % MOD;
        inv[i] = binpow(fact[i], MOD - 2);
    }
}

int nCr(int n, int r) {
    if (r > n || r < 0) return 0;
    return fact[n] * inv[r] % MOD * inv[n - r] % MOD;
}
```

---

## 🧩 5. Casos Comuns

### Subconjuntos de um conjunto com `n` elementos:

```
2ⁿ subconjuntos
```

### Distribuição com repetição (princípio das gavetas):

- Ex: Quantos inteiros positivos somam `n` com `k` termos?
```text
Resposta: C(n - 1, k - 1)
```

---

## 🧪 6. Combinatória com restrições

- **Permutação com repetição**:  
  `n! / (a! b! c! ...)`  
  Ex: Letras da palavra "BANANA"

- **Combinatória com inclusão e exclusão**  
  (problemas do tipo "quantos não têm essa propriedade")

---

## 🔧 7. Dicas de competição

- Pré-calcule `fatorial` e `inverso modular` até `1e6`
- Sempre use `% MOD` após cada operação
- Cuidado com overflow: use `int64_t` (`long long`)
- Trate `nCr(n, r)` com `r > n` como `0`
- Use `bitmasks` para gerar subconjuntos pequenos

---

## 📚 Referências

- [CP Algorithms - Combinatorics](https://cp-algorithms.com/combinatorics/binomial-coefficients.html)
- [GeeksForGeeks - Combinatorics](https://www.geeksforgeeks.org/introduction-to-combinatorics/)
- [nCr pré-processado](https://codeforces.com/blog/entry/22197)

---

Este documento faz parte da seção [`competitive_programming/math`](./), dedicada a técnicas eficientes de contagem para maratonas.
