# 🌐 Docker Network Management

Este documento trata exclusivamente da criação, inspeção e gerenciamento de redes no Docker. A rede é um componente essencial para a comunicação entre containers, serviços e com o mundo externo.

---

## 🧠 Conceitos

- **Bridge Network**: Padrão para containers em um mesmo host. Isola containers entre si e do host.
- **Host Network**: Compartilha a pilha de rede do host. Container não tem IP próprio.
- **None Network**: Sem rede. Nenhuma interface de rede é atribuída ao container.
- **User-defined Network**: Redes criadas pelo usuário com escopo personalizado e DNS interno.

---

## 🔧 Criar e listar redes

Criar uma rede bridge customizada:
```bash
docker network create minha-rede
```

Listar redes existentes:
```bash
docker network ls
```

Inspecionar rede específica:
```bash
docker network inspect minha-rede
```

Remover rede (se não estiver em uso):
```bash
docker network rm minha-rede
```

---

## 🔌 Conectar e desconectar containers

Executar container já conectado a uma rede:
```bash
docker run -d --name meu-app --network=minha-rede nginx
```

Conectar container existente:
```bash
docker network connect minha-rede meu-container
```

Desconectar container:
```bash
docker network disconnect minha-rede meu-container
```

---

## 📡 Comunicações entre containers

Containers na mesma rede podem se comunicar via DNS interno (nome do container):
```bash
curl http://nome-do-container:porta
```

Exemplo com dois containers:
```bash
docker network create app-net

docker run -d --name db --network app-net postgres

docker run -it --rm --network app-net postgres psql -h db -U postgres
```

---

## 🛠️ Usando com `docker-compose`

Por padrão, o Compose cria uma rede para os serviços:
```yaml
services:
  web:
    image: nginx
  app:
    image: myapp
    depends_on:
      - web
```

Todos os serviços estarão em uma mesma rede chamada `nome-do-projeto_default`, e poderão se comunicar por nome do serviço.

---

## 🧪 Boas práticas

- Use redes nomeadas para organização clara entre ambientes.
- Separe redes por contexto: `frontend`, `backend`, `db-net`.
- Evite `--network host` exceto quando necessário.
- Teste a comunicação entre containers com `ping`, `curl`, `nc`.

---

## 🔍 Referências

- [Docker Networks - Docs](https://docs.docker.com/network/)
- [Bridge vs Host vs None](https://docs.docker.com/network/drivers/)
- [Best Practices for Docker Networking](https://docs.docker.com/network/network-tutorial-standalone/)

---

Este conteúdo faz parte da [pasta de estudos Docker](../docker/) do repositório [`study`](attachs/docs/README.md).

📌 *Containers, volumes e imagens estão documentados separadamente.*