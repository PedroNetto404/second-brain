# 🧮 Aritmética Modular

A aritmética modular é uma técnica usada para operar com números sob um **módulo fixo**, evitando overflow e respeitando congruências.

> Exemplo: `17 mod 5 = 2` porque 17 deixa resto 2 ao ser dividido por 5.

---

## 🧠 1. Definição

Dado um número `a` e um módulo `m`, dizemos que:

```
a ≡ b (mod m) ⇔ (a - b) é múltiplo de m
```

---

## 🔁 2. Propriedades Básicas

Se `a ≡ b (mod m)` e `c ≡ d (mod m)`, então:

- `(a + c) ≡ (b + d) (mod m)`
- `(a - c) ≡ (b - d) (mod m)`
- `(a * c) ≡ (b * d) (mod m)`
- ⚠️ Divisão modular exige **inverso multiplicativo**

---

## 🧮 3. Implementação Modular em C++

```cpp
const int MOD = 1e9 + 7;

int mod(int a) {
    return ((a % MOD) + MOD) % MOD;
}
```

✅ Corrige negativos: `mod(-3) = 1000000004`

---

## ➕ 4. Soma e Multiplicação Modular

```cpp
int add(int a, int b) {
    return (a + b) % MOD;
}

int mul(int a, int b) {
    return (a * b) % MOD;
}
```

---

## 🔼 5. Exponenciação Modular (binária)

```cpp
int binpow(int a, int b) {
    int res = 1;
    a %= MOD;
    while (b > 0) {
        if (b & 1)
            res = res * a % MOD;
        a = a * a % MOD;
        b >>= 1;
    }
    return res;
}
```

---

## 🧩 6. Inverso Modular

Para `MOD` primo, o inverso de `a` é `a⁻¹ ≡ a^(MOD-2) mod MOD`.

```cpp
int modinv(int a) {
    return binpow(a, MOD - 2);
}
```

⚠️ Apenas se `a` e `MOD` forem coprimos (gcd(a, MOD) = 1)

---

## 📊 7. Divisão Modular

```cpp
int divide(int a, int b) {
    return a * modinv(b) % MOD;
}
```

---

## 🧪 8. Aplicações Típicas

- Contagem com grandes números (combinatória, DP)
- Probabilidades (divisão modular)
- Teorema de Fermat Pequeno (`a^(p-1) ≡ 1 mod p`)
- Números grandes em crivos, fatorial, etc.
- Enunciados com "responda módulo `1e9+7`"

---

## 📚 Referências

- [CP Algorithms - Modular Arithmetic](https://cp-algorithms.com/math/modular-arithmetic.html)
- [Inverso Modular - GeeksForGeeks](https://www.geeksforgeeks.org/multiplicative-inverse-under-modulo-m/)
- [Khan Academy - Congruência Modular](https://pt.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/congruence-modulo)

---

Este arquivo faz parte da seção [`competitive_programming/math`](./), essencial para lidar com limites numéricos e modularização de resultados em maratonas.
