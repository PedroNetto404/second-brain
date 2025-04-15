# 📦 Container Management

Este documento reúne todos os comandos e boas práticas voltados exclusivamente para o **gerenciamento de containers Docker**, incluindo execução, inspeção, logs, entrada em shell, reinicialização, entre outros. 

Volumes, redes e imagens serão abordados em documentos separados.

---

## 🧠 Conceitos

- **Container**: Uma instância de uma imagem Docker em execução. Representa um processo isolado com seu próprio sistema de arquivos e ambiente.
- **ID/Nome do container**: Identificador curto ou nome atribuído ao container que será usado em comandos de gerenciamento.

---

## ▶️ Criar e executar um container

Executa um container interativamente:
```bash
docker run -it ubuntu bash
```

Executa em background (detached mode):
```bash
docker run -d --name meu-container nginx
```

Executa com remoção automática após término:
```bash
docker run --rm alpine echo "Container finalizado"
```

---

## 🛑 Parar, iniciar, reiniciar e remover

Parar um container:
```bash
docker stop meu-container
```

Iniciar novamente:
```bash
docker start meu-container
```

Reiniciar:
```bash
docker restart meu-container
```

Remover (parado ou com `--force`):
```bash
docker rm meu-container
```

Forçar remoção de container em execução:
```bash
docker rm -f meu-container
```

Remover todos os containers parados:
```bash
docker container prune
```

---

## 📋 Listar containers

Listar containers ativos:
```bash
docker ps
```

Listar todos os containers (ativos e parados):
```bash
docker ps -a
```

---

## 🔍 Inspecionar containers

Ver detalhes completos em JSON:
```bash
docker inspect meu-container
```

Ver IP do container:
```bash
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' meu-container
```

Ver status, nomes, mounts, etc.:
```bash
docker container inspect meu-container
```

---

## 📄 Ver logs do container

Logs padrão (STDOUT/STDERR):
```bash
docker logs meu-container
```

Seguir logs em tempo real:
```bash
docker logs -f meu-container
```

Ver logs com timestamps:
```bash
docker logs -ft meu-container
```

---

## 💻 Acessar o terminal do container

Entrar com bash (se disponível):
```bash
docker exec -it meu-container bash
```

Entrar com sh (para Alpine ou containers leves):
```bash
docker exec -it meu-container sh
```

Executar comando único:
```bash
docker exec -it meu-container ls /app
```

---

## 📦 Nomear containers e organização

Ao criar containers, nomeie-os para facilitar manutenção:
```bash
docker run --name db-postgres -d postgres:15
```

Ver nome atribuído automaticamente:
```bash
docker ps --format "table {{.ID}}	{{.Image}}	{{.Names}}"
```

---

## 🧪 Boas práticas

- Sempre nomeie seus containers com `--name`.
- Use `--rm` para execuções temporárias.
- Use `-it` para interações manuais (shell/bash).
- Use `-d` para serviços em background.
- Automatize a limpeza com `docker container prune` em ambientes de testes.

---

## 🔍 Referências

- [Docker CLI - Container Commands](https://docs.docker.com/engine/reference/commandline/container/)
- [Docker Tips by Bret Fisher](https://github.com/BretFisher/docker-tips)
- [Cheatsheet - Docker Containers](https://github.com/wsargent/docker-cheat-sheet#container-management)

---

Este conteúdo faz parte da [pasta de estudos Docker](../docker/) do repositório [`study`](../README.md).

📌 *Volumes, redes e construção de imagens serão tratados em arquivos complementares.*

