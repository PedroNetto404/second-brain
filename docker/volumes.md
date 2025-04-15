# 📁 Docker Volume Management

Este documento cobre exclusivamente a criação, uso e gerenciamento de volumes Docker — o principal mecanismo de persistência de dados entre execuções e recriações de containers.

---

## 🧠 Conceitos

- **Volume**: Um diretório gerenciado pelo Docker armazenado no host e acessado por containers.
- **Bind mount**: Mapeamento de um diretório específico do host para dentro do container.
- **Anonymous volumes**: Volumes criados implicitamente sem nome, úteis para testes mas difíceis de gerenciar.

---

## 🔧 Criar e listar volumes

Criar volume nomeado:
```bash
docker volume create meu-volume
```

Listar volumes existentes:
```bash
docker volume ls
```

Inspecionar volume específico:
```bash
docker volume inspect meu-volume
```

Remover volume:
```bash
docker volume rm meu-volume
```

Remover volumes não utilizados:
```bash
docker volume prune
```

---

## 📦 Usar volumes em containers

Montar volume nomeado:
```bash
docker run -d --name web --mount source=meu-volume,target=/usr/share/nginx/html nginx
```

Ou usando `-v`:
```bash
docker run -d --name web -v meu-volume:/usr/share/nginx/html nginx
```

Montar diretório local (bind mount):
```bash
docker run -d -v $(pwd)/dados:/data busybox
```

Criar container com volume anônimo:
```bash
docker run -v /data busybox
```

---

## 📂 Explorar dados de volumes

Ver conteúdo diretamente (bind mount):
```bash
ls ./dados
```

Com volumes nomeados:
```bash
docker run --rm -v meu-volume:/data alpine ls /data
```

Copiar arquivos para volume:
```bash
docker cp arquivo.txt meu-container:/data
```

---

## 🛠️ Usar com `docker-compose`

Exemplo `docker-compose.yml`:
```yaml
services:
  app:
    image: postgres
    volumes:
      - dados-db:/var/lib/postgresql/data

volumes:
  dados-db:
```

---

## 🧪 Boas práticas

- Nomeie volumes explicitamente para facilitar o gerenciamento.
- Prefira volumes a bind mounts para persistência de dados sensível.
- Use `volume inspect` para entender o uso e localização real.
- Nunca armazene dados críticos em volumes anônimos.

---

## 🔍 Referências

- [Docker Volumes - Docs](https://docs.docker.com/storage/volumes/)
- [Docker Compose - Volumes](https://docs.docker.com/compose/compose-file/compose-file-v3/#volumes)
- [Volume vs Bind Mount](https://docs.docker.com/storage/#choose-the-right-type-of-mount)

---

Este conteúdo faz parte da [pasta de estudos Docker](../docker/) do repositório [`study`](../README.md).

📌 *Containers, redes e imagens estão documentados separadamente.*