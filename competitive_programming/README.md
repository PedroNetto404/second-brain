# 🏁 Competitive Programming

Este diretório reúne conteúdos, técnicas, algoritmos e templates voltados para **programação competitiva**, com foco em resolução de problemas, otimização e preparação para maratonas como Interfatec, ICPC, OBMEP e afins.

A linguagem principal adotada é **C++** (`C++17` ou superior), devido à sua performance, biblioteca padrão rica (`STL`) e uso predominante em competições oficiais.

---

## 🎯 Objetivos

- Consolidar teoria de algoritmos e estruturas de dados
- Praticar resolução de problemas por nível e por categoria
- Montar um repositório de referência rápido para maratonas
- Manter templates e snippets prontos para uso

---

## 📁 Estrutura

```bash
competitive_programming/
├── basics/              # Entrada/saída, complexidade
├── math/                # GCD, mod, combinatória
├── strings/             # KMP, trie, hashing
├── dp/                  # Memoização, bottom-up
├── graphs/              # DFS, BFS, Dijkstra, Union-Find
├── greedy/              # Seleção de atividades, lógica gulosa
├── search/              # Busca binária, ternária, BFS/DFS
├── geometry/            # Geometria computacional
├── number-theory/       # Crivo, teoremas, fatoração
├── ad-hoc/              # Bitmasks, simulações, bruteforce
├── templates/           # Snippets e macros em C++
├── problems/            # Listas por tema ou dificuldade
└── README.md            # Este índice
```

---

## 📚 Tópicos Cobertos

### Básicos
- [input-output.md](basics/input-output.md): Fast IO em C++
- [complexity.md](basics/complexity.md): Análise de tempo e espaço

### Matemática
- [gcd-lcm.md](math/gcd-lcm.md)
- [modular-arithmetic.md](math/modular-arithmetic.md)
- [combinatorics.md](math/combinatorics.md)

### Strings
- [pattern-matching.md](strings/pattern-matching.md)
- [kmp.md](strings/kmp.md)
- [trie.md](strings/trie.md)

### Programação Dinâmica
- [knapsack.md](dp/knapsack.md)
- [lis.md](dp/lis.md)
- [memoization.md](dp/memoization.md)

### Grafos
- [dfs-bfs.md](graphs/dfs-bfs.md)
- [dijkstra.md](graphs/dijkstra.md)
- [union-find.md](graphs/union-find.md)

### Outros
- [bitmasks.md](ad-hoc/bitmasks.md)
- [fast-io.md](templates/fast-io.md)
- [by-topic.md](problems/by-topic.md)

---

## 🧪 Preparação para Competições

- 🏁 Use arquivos da pasta `templates/` para acelerar sua entrada no problema
- 📈 Resolva problemas por tópico para consolidar técnica
- ⏱️ Pratique com tempo limite (ex: 30 min por problema)
- 🧠 Revise após cada problema: complexidade, alternativas, padrões

---

## 📌 Linguagem Padrão: `C++`

Motivos:
- STL com `vector`, `set`, `map`, `priority_queue`, etc
- Algoritmos rápidos (`sort`, `lower_bound`, `binary_search`)
- Macros e `typedefs` para produtividade
- `cin/cout` otimizável com `ios_base::sync_with_stdio(false)`

> Para configuração de compilador, veja [templates/cpp-snippets.md](templates/cpp-snippets.md)

---

## 🛠️ Ambiente Recomendado

- Linux ou WSL com `g++` (`-std=c++17`)
- Editor leve como VSCode, Sublime ou Vim
- Teste local com arquivos `.in` / `.out`
- Use `./run.sh` para compilar e testar automaticamente

---

## 📚 Referências Úteis

- [CP-Algorithms](https://cp-algorithms.com/)
- [GeeksForGeeks - Competitive](https://www.geeksforgeeks.org/fundamentals-of-algorithms/)
- [CSES Problem Set](https://cses.fi/problemset/)
- [AtCoder Library](https://github.com/atcoder/ac-library)
- [Neps Academy](https://neps.academy/)

---

Este diretório faz parte de [`study/`](../), e serve como base sólida para quem quer treinar lógica, velocidade e precisão para provas competitivas.
