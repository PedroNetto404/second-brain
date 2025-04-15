# ⚡ Fast IO em C++ para Competições

Em problemas com entrada/saída intensiva, usar métodos rápidos de leitura e escrita pode ser a **diferença entre AC e TLE**. Este arquivo apresenta técnicas otimizadas de IO para **programação competitiva em C++**.

---

## 🧪 1. Desativar Sincronização com `iostream`

```cpp
ios_base::sync_with_stdio(false);
cin.tie(NULL);
```

Coloque isso no início da `main()` para acelerar significativamente o uso de `cin` e `cout`.

### Exemplo completo:

```cpp
int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);

    int n;
    cin >> n;
    cout << n * 2 << '\n';

    return 0;
}
```

---

## 🚀 2. Substituir `endl` por `'\n'`

```cpp
cout << "Resultado" << '\n'; // ✅ Rápido
cout << "Resultado" << endl; // ❌ Desnecessário (flush automático = lento)
```

---

## 📦 3. Entrada e Saída via `scanf/printf` (quando for o caso)

Embora `cin/cout` com sync desativado seja rápido, `scanf/printf` ainda pode ser mais rápido em casos extremos:

```cpp
int a;
scanf("%d", &a);
printf("%d\n", a);
```

⚠️ Evite misturar `scanf` com `cin`, ou `printf` com `cout`.

---

## 🧾 4. Leitura de Arquivo (para debug offline)

```cpp
#ifndef ONLINE_JUDGE
    freopen("input.txt", "r", stdin);
    freopen("output.txt", "w", stdout);
#endif
```

Coloque no início da `main()` para ler de arquivos locais durante testes.

---

## 🧮 5. Leitura em Bloco com `getline()` e `stringstream`

```cpp
string linha;
getline(cin, linha);
stringstream ss(linha);

int x;
while (ss >> x) {
    // processa x
}
```

✅ Útil para parsing de linhas com dados variados.

---

## 🛠️ 6. Leitor Personalizado (super avançado)

Para casos extremos:

```cpp
int fastReadInt() {
    int x = 0, c = getchar();
    while (c < '0' || c > '9') c = getchar();
    while (c >= '0' && c <= '9') {
        x = x * 10 + c - '0';
        c = getchar();
    }
    return x;
}
```

⚠️ Use apenas quando `cin` for insuficiente mesmo com sync desabilitado.

---

## 📚 Referências

- [CP Algorithms - Input/Output](https://cp-algorithms.com/cpp/io.html)
- [USACO Guide - Fast IO](https://usaco.guide/general/fast-io/)
- [GeeksForGeeks - Fast I/O in C++](https://www.geeksforgeeks.org/fast-io-for-competitive-programming/)

---

Este documento faz parte da seção [`templates`](./), com foco em maximizar performance de leitura/escrita em competições com grandes entradas.
