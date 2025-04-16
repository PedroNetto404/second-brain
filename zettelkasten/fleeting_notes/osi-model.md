# 🌐 OSI Model (Open Systems Interconnection)

O modelo **OSI** é uma estrutura conceitual em sete camadas usada para entender e padronizar como os dados se movem em uma rede de computadores. Cada camada executa uma função específica e se comunica com as camadas imediatamente acima e abaixo.

---

## 📚 Visão Geral

```
+------------------+-----------------------------+
| Camada 7         | Aplicação (Application)     |
| Camada 6         | Apresentação (Presentation) |
| Camada 5         | Sessão (Session)            |
| Camada 4         | Transporte (Transport)      |
| Camada 3         | Rede (Network)              |
| Camada 2         | Enlace de Dados (Data Link) |
| Camada 1         | Física (Physical)           |
+------------------+-----------------------------+
```

---

## 🔎 Descrição das Camadas

### 1️⃣ Camada Física (Physical)

- Transmissão de bits brutos por meios físicos.
- Define cabos, sinais, conectores, modulação.

**Exemplos:** Ethernet física, cabo UTP, fibra óptica, Bluetooth, USB.

---

### 2️⃣ Camada de Enlace (Data Link)

- Empacota bits em quadros (frames).
- Controle de acesso ao meio e detecção de erros.

**Exemplos:** Ethernet (802.3), Wi-Fi (802.11), switches.

---

### 3️⃣ Camada de Rede (Network)

- Roteamento entre redes diferentes.
- Endereçamento lógico e seleção de caminhos.

**Exemplos:** IP, ICMP, ARP, roteadores.

---

### 4️⃣ Camada de Transporte (Transport)

- Entrega fim-a-fim com confiabilidade opcional.
- Controle de fluxo e multiplexação.

**Exemplos:** TCP, UDP, portas (80, 443).

---

### 5️⃣ Camada de Sessão (Session)

- Estabelecimento, controle e finalização de sessões.
- Sincronização e gerenciamento de estado.

**Exemplos:** NetBIOS, RPC, APIs de sessão.

---

### 6️⃣ Camada de Apresentação (Presentation)

- Tradução, compressão e criptografia de dados.
- Converte dados entre o formato da aplicação e da rede.

**Exemplos:** SSL/TLS, JPEG, MPEG, UTF-8.

---

### 7️⃣ Camada de Aplicação (Application)

- Interface entre a aplicação do usuário e a rede.
- Define protocolos de alto nível.

**Exemplos:** HTTP, FTP, SSH, DNS, SMTP.

---

## 🧠 Mnemônicos

- De cima para baixo: `All People Seem To Need Data Processing`
- De baixo para cima: `Please Do Not Throw Sausage Pizza Away`

---

## 🔄 Comparação OSI vs TCP/IP

| OSI (Camada)             | TCP/IP               |
|--------------------------|----------------------|
| Aplicação (7, 6, 5)      | Aplicação            |
| Transporte (4)           | Transporte           |
| Rede (3)                 | Internet             |
| Enlace + Física (2, 1)   | Acesso à Rede        |

---

## 🧪 Diagnóstico por Camada

- ❌ Sem link físico → Camada 1
- ❌ Sem endereço ou IP inválido → Camada 3
- ❌ Sem conexão TCP/UDP → Camada 4
- ❌ Serviço não responde (HTTP, DNS) → Camada 7

---

```mermaid
graph TD
    C7[Camada 7: Aplicação]
    C6[Camada 6: Apresentação]
    C5[Camada 5: Sessão]
    C4[Camada 4: Transporte]
    C3[Camada 3: Rede]
    C2[Camada 2: Enlace de Dados]
    C1[Camada 1: Física]

    C7 -->|Protocolos (HTTP, DNS)| C6
    C6 -->|Conversão, Criptografia| C5
    C5 -->|Gerência de Sessões| C4
    C4 -->|TCP, UDP, Portas| C3
    C3 -->|IP, Roteamento| C2
    C2 -->|MAC, Framing, Switches| C1
    C1 -->|Cabos, Sinais, Bits| FIM[Física]

    classDef camada fill:#c5e1a5,stroke:#33691e,color:#000;
    class C7,C6,C5,C4,C3,C2,C1 camada
```

## 📚 Referências

- RFC 1122 - Host Requirements: https://datatracker.ietf.org/doc/html/rfc1122  
- Cloudflare OSI Overview: https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/  
- Wikipedia - OSI Model: https://en.wikipedia.org/wiki/OSI_model

---

Este documento faz parte da [pasta de redes](../networks/) do repositório [`study`](attachs/docs/README.md).
