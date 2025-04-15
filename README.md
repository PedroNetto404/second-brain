# 🧠 study

> Repositório de estudos técnicos e experimentações práticas em diversas tecnologias, linguagens e ferramentas de desenvolvimento.

Este repositório organiza os conteúdos por área de conhecimento, facilitando a navegação, aprofundamento e revisitação de tópicos importantes no dia a dia de um engenheiro de software.

---

## 📁 Estrutura

Cada subdiretório corresponde a um tema ou tecnologia específica. Dentro de cada pasta, os arquivos são organizados por anotações, exemplos práticos, projetos experimentais, diagramas e links úteis.

```bash
study/
├── all.md              # Índice consolidado de anotações (se aplicável)
├── docker/             # Containers, Dockerfile, docker-compose, internals
├── networks/           # Fundamentos de redes, TCP/IP, NAT, roteamento, DNS
├── so/                 # Teoria de sistemas operacionais e foco em Linux
├── csharp/             # Fundamentos de C#, .NET, EF Core, APIs REST
├── golang/             # Go, DDD, Clean Architecture, concurrency
├── linux/              # Comandos, administração, scripts, perf, net, file systems
├── git/                # Comandos, fluxos, git hooks, submodules, rebase
├── postgres/           # SQL, PL/pgSQL, índices, performance tuning
├── python/             # Scripts, data science, Flask/Django, PEP8
├── machine-learning/   # Fundamentos, regressão, classificação
├── kubernetes/         # kubectl, manifests, Helm, operadores
├── rust/               # Ownership, borrow checker, cargo, macros
└── README.md           # Este arquivo
```

> 📌 *A estrutura pode evoluir conforme novos temas forem sendo estudados.*

---

## 🎯 Objetivo

- Consolidar conhecimento adquirido em cursos, livros, artigos e projetos reais.
- Servir como referência rápida e confiável para revisões técnicas.
- Manter um histórico versionado do aprendizado contínuo.
- Documentar experimentações com ferramentas e práticas modernas.

---

## 📚 Conteúdos de Destaque

### ✅ Docker
- [`architecture.md`](docker/architecture.md): visão geral da engine e componentes
- [`containers.md`](docker/containers.md): instanciamento e gerenciamento de containers
- [`logs.md`](docker/logs.md): drivers, rotação e centralização de logs
- [`volumes.md`](docker/volumes.md): persistência de dados com volumes
- [`networking.md`](docker/networking.md): criação, inspeção e uso de redes Docker

### ✅ Redes (Networking)
- [`osi-model.md`](networks/osi-model.md): camadas, responsabilidades e protocolos
- [`ip-subnetting.md`](networks/ip-subnetting.md): CIDR, máscaras, endereçamento
- [`routing.md`](networks/routing.md): roteamento estático e dinâmico, tabelas e protocolos
- [`dns.md`](networks/dns.md): resolução de nomes, zonas, cache e segurança

### ✅ Sistemas Operacionais
- [`intro/`](so/intro/): fundamentos, história e tipos de sistemas operacionais
- [`processes/`](so/processes/): processos, threads, escalonamento e sinais
- [`memory/`](so/memory/): memória virtual, paginação, segmentação e alocação
- [`filesystem/`](so/filesystem/): estrutura de arquivos, permissões, montagem
- [`io/`](so/io/): gerenciamento de dispositivos, drivers, buffering e syscalls
- [`concurrency/`](so/concurrency/): mutexes, semáforos, IPC e políticas de escalonamento
- [`security/`](so/security/): usuários, grupos, ACLs e isolamento
- [`linux/`](so/linux/): boot, init, systemd, procfs e ferramentas ps
- [`advanced/`](so/advanced/): kernel, módulos, cgroups, namespaces e tempo real

### ✅ C#
- Projetos com .NET 8
- APIs REST com EF Core 8
- Background services e injeção de dependência

### ✅ Go
- Arquitetura hexagonal e DDD
- Gin, SQLX, MongoDB Driver
- Estrutura de monorepo com `cmd/`, `internal/`, `pkg/`

E muito mais...

---

## 🛠️ Como usar

Clone o repositório:

```bash
git clone https://github.com/seu-usuario/study.git
cd study
```

Explore as pastas conforme seu interesse e utilize qualquer conteúdo como referência ou ponto de partida para seus próprios projetos.

---

## ✍️ Autor

Pedro Netto  
Engenheiro de Software • Apaixonado por Clean Code
[LinkedIn](https://www.linkedin.com/in/nettopedro/) • [GitHub](https://github.com/PedroNetto404)
