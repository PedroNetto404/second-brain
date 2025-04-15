# 📎 Snippets e Macros em C++ para Competições

Este documento reúne **atalhos**, **boilerplates** e **macros úteis** para acelerar o desenvolvimento durante competições de programação, com foco em **C++17+**.

---

## 🧱 1. Template Base

```cpp
#include <bits/stdc++.h>
using namespace std;

#define int long long
#define endl '\n'
#define pb push_back
#define all(x) x.begin(), x.end()
#define fastio ios_base::sync_with_stdio(false); cin.tie(NULL);

typedef vector<int> vi;
typedef pair<int, int> pii;

const int INF = 1e18;
const int MOD = 1e9 + 7;

int32_t main() {
    fastio;
    
    int t = 1;
    // cin >> t;
    while (t--) {
        // solve();
    }

    return 0;
}
```

---

## 📋 2. Atalhos Comuns

```cpp
#define rep(i,a,b) for(int i=a; i<b; i++)
#define rrep(i,a,b) for(int i=a; i>=b; i--)
#define sz(x) (int)(x).size()
#define YES cout << "YES\n"
#define NO cout << "NO\n"
```

---

## 📊 3. Debug Rápido

```cpp
#define dbg(x) cerr << #x << " = " << x << endl;
```

Use com:

```cpp
int x = 42;
dbg(x); // x = 42
```

---

## 🔄 4. Leitura de Vetores

```cpp
template<typename T>
void readv(vector<T> &v, int n) {
    v.resize(n);
    for (auto &x : v) cin >> x;
}
```

---

## 📚 5. Pré-cálculo de Fatorial / Inverso Modular

```cpp
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
    if (r > n) return 0;
    return fact[n] * inv[r] % MOD * inv[n - r] % MOD;
}
```

---

## 🧮 6. Funções Úteis

```cpp
bool is_prime(int n) {
    if (n < 2) return false;
    for (int i = 2; i*i <= n; i++)
        if (n % i == 0) return false;
    return true;
}
```

```cpp
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}
```

```cpp
int lcm(int a, int b) {
    return a / gcd(a, b) * b;
}
```

---

## 💡 7. Tips de Competição

- Sempre comece com `fastio`
- Troque `int` por `int64_t` se usar C++20 (`#include <cstdint>`)
- Use `priority_queue<pair<int,int>, vector<pair<int,int>>, greater<>>` para Dijkstra
- Utilize `map<int, int>` ou `unordered_map<int, int>` com cuidado em limites de tempo
- Precompile suas funções antes da competição (ou tenha em snippet)

---

## 🔗 Referências

- [cp-algorithms.com](https://cp-algorithms.com/)
- [C++ STL Cheatsheet (Byte-by-Byte)](https://github.com/Byte-by-Byte/cheat-sheets/blob/master/C%2B%2B-Cheat-Sheet.pdf)
- [USACO Guide](https://usaco.guide/general/fast-io/)

---

Este arquivo faz parte da seção [`templates`](./), voltada para inicialização
