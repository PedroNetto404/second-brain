# 🧾 Entrada e Saída (Input/Output) em C++ para Competições

Este documento cobre os formatos mais comuns de entrada e saída em problemas competitivos, com exemplos didáticos em **C++**, considerando boas práticas e variações esperadas nas maratonas.

---

## ⚙️ 1. Entrada padrão simples

```cpp
int n;
cin >> n;
```

Entrada:
```
42
```

---

## 📋 2. Entrada de múltiplos valores

```cpp
int a, b;
cin >> a >> b;
```

Entrada:
```
3 5
```

---

## 📚 3. Leitura de vetores

```cpp
int n;
cin >> n;
vector<int> v(n);
for (int &x : v) cin >> x;
```

Entrada:
```
5
10 20 30 40 50
```

---

## 🧾 4. Leitura até EOF (end of file)

```cpp
int x;
while (cin >> x) {
    // processa x
}
```

✅ Comum em problemas de leitura indefinida (ex: URI/Beecrowd)

---

## 🧵 5. Leitura de strings com espaços

```cpp
string linha;
getline(cin, linha);
```

Entrada:
```
Olá mundo com espaço
```

⚠️ Use `cin.ignore()` antes de `getline()` se houver `cin` antes.

---

## 📦 6. Saída formatada

```cpp
cout << fixed << setprecision(2) << resultado << '\n';
```

Imprime com 2 casas decimais:
```
3.14
```

---

## 🚫 7. Evite erros comuns

| Problema                             | Solução                                       |
|--------------------------------------|-----------------------------------------------|
| `endl` lento                         | Use `'\n'`                                    |
| `cin >>` antes de `getline()`        | Use `cin.ignore()`                            |
| Misturar `cin` com `scanf`           | Evite → escolha uma abordagem e mantenha      |
| Leitura incorreta de `char`/`string`| Atenção ao tipo e ao `getline` com espaços    |

---

## 🧪 8. Leitura em matrizes

```cpp
int n, m;
cin >> n >> m;
vector<vector<int>> mat(n, vector<int>(m));

for (int i = 0; i < n; i++)
    for (int j = 0; j < m; j++)
        cin >> mat[i][j];
```

Entrada:
```
2 3
1 2 3
4 5 6
```

---

## 🎯 9. Entrada de múltiplos casos de teste

### Formato 1: Número de casos

```cpp
int t;
cin >> t;
while (t--) {
    // resolva o caso
}
```

Entrada:
```
3
caso1
caso2
caso3
```

### Formato 2: Até EOF

```cpp
while (cin >> a >> b) {
    // processa
}
```

---

## 🧰 10. Fast IO padrão

```cpp
ios_base::sync_with_stdio(false);
cin.tie(NULL);
```

Sempre coloque isso no início da `main()`.

---

## 📚 Referências

- [CP Algorithms - I/O](https://cp-algorithms.com/cpp/io.html)
- [GeeksForGeeks - Input in C++](https://www.geeksforgeeks.org/basic-input-output-c/)
- [Beecrowd - Guia de Entrada/Saída](https://www.beecrowd.com.br/judge/pt/faq)

---

Este arquivo faz parte da seção [`competitive_programming/basics`](./), cobrindo fundamentos essenciais para leitura e escrita eficientes em problemas de maratona.
