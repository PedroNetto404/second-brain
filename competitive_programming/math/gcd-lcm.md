# 🔢 GCD e LCM em Programação Competitiva

Este documento cobre os algoritmos para cálculo de **MDC (máximo divisor comum)** e **MMC (mínimo múltiplo comum)**, fundamentais para problemas de divisibilidade, frações, ciclos e simplificações.

---

## 🧠 Definições

- **GCD(a, b)**: Maior inteiro que divide `a` e `b`.
- **LCM(a, b)**: Menor inteiro positivo divisível por `a` e `b`.

> Relação importante:
```math
lcm(a, b) = |a * b| / gcd(a, b)
```

---

## 🔁 1. Algoritmo de Euclides (recursivo)

```cpp
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}
```

---

## 🔁 2. Algoritmo de Euclides (iterativo)

```cpp
int gcd(int a, int b) {
    while (b != 0) {
        int r = a % b;
        a = b;
        b = r;
    }
    return a;
}
```

---

## 🔁 3. LCM com GCD

```cpp
int lcm(int a, int b) {
    return a / gcd(a, b) * b;
}
```

⚠️ **Evite `a * b` diretamente antes da divisão** para prevenir overflow em C++.

---

## 🧮 4. GCD de múltiplos números

```cpp
int gcd_list(const vector<int>& v) {
    int res = v[0];
    for (int i = 1; i < v.size(); i++)
        res = gcd(res, v[i]);
    return res;
}
```

---

## 🧪 5. Aplicações Práticas

| Problema                        | Uso                         |
|---------------------------------|------------------------------|
| Simplificar frações             | `gcd(num, den)`             |
| Sincronizar ciclos              | `lcm(a, b)`                 |
| Reduzir divisores comuns        | `gcd` entre N números       |
| Resolver congruências modulares| uso em CRT (teorema chinês) |

---

## 💡 6. Propriedades Úteis

- `gcd(a, 0) = |a|`
- `gcd(a, b) = gcd(b, a % b)`
- Se `a % b == 0` então `gcd(a, b) = b`
- `gcd(a, b) * lcm(a, b) = |a * b|`

---

## ⚙️ 7. Built-in em C++17+

```cpp
#include <numeric> // std::gcd, std::lcm

int a = 30, b = 18;
int d = gcd(a, b); // C++17
int m = lcm(a, b); // C++17
```

⚠️ Em competições, use sua própria versão para compatibilidade com C++14.

---

## 📚 Referências

- [CP Algorithms - GCD](https://cp-algorithms.com/algebra/euclid-algorithm.html)
- [GCD/LCM - GeeksForGeeks](https://www.geeksforgeeks.org/lcm-and-gcd/)
- [Euclidean Algorithm - Khan Academy](https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/the-euclidean-algorithm)

---

Este arquivo faz parte da seção [`competitive_programming/math`](./), cobrindo ferramentas algébricas básicas e eficientes para uso em maratonas.
