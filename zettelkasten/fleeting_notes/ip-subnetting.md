# 🌐 IP e Subnetting

Este documento apresenta os conceitos fundamentais de **endereçamento IP** (IPv4) e **subnetting**, que são essenciais para segmentar redes, controlar tráfego e definir hierarquias de roteamento em infraestruturas de rede.

---

## 📦 Endereçamento IPv4

Um endereço IPv4 é composto por **32 bits**, geralmente representado no formato decimal com quatro octetos:

```text
Exemplo: 192.168.10.25
```

Cada octeto representa 8 bits, e o total de combinações possíveis é 2³² (4.294.967.296 endereços).

---

## 🧠 Classes de IP (histórico)

| Classe | Intervalo Inicial      | Destino                     |
|--------|------------------------|-----------------------------|
| A      | 1.0.0.0 a 126.255.255.255 | Grandes organizações      |
| B      | 128.0.0.0 a 191.255.255.255 | Médias organizações       |
| C      | 192.0.0.0 a 223.255.255.255 | Pequenas redes             |
| D      | 224.0.0.0 a 239.255.255.255 | Multicast                  |
| E      | 240.0.0.0 a 255.255.255.255 | Experimental (reservado)   |

> ⚠️ Hoje o conceito de classes é obsoleto: utilizamos **CIDR** para definir intervalos.

---

## 🧩 CIDR e Máscara de Sub-rede

- **CIDR**: Classless Inter-Domain Routing — notação como `192.168.1.0/24`.
- O número após a barra indica o **número de bits da máscara de rede**.

### Exemplos

| CIDR      | Máscara Sub-rede       | IPs utilizáveis | Bloco             |
|-----------|------------------------|------------------|-------------------|
| /8        | 255.0.0.0              | 16.777.214       | 10.0.0.0 → 10.255.255.255 |
| /16       | 255.255.0.0            | 65.534           | 192.168.0.0/16     |
| /24       | 255.255.255.0          | 254              | 192.168.1.0/24     |
| /30       | 255.255.255.252        | 2                | 192.168.1.0/30     |

> ✅ **IPs utilizáveis** excluem o endereço de rede e o de broadcast.

---

## 🧮 Cálculo de Subnetting

Fórmulas básicas:

- **Hosts possíveis**: `2^(32 - máscara) - 2`
- **Número de sub-redes**: depende do número de bits emprestados da parte de host

Exemplo: Quantos hosts há em uma sub-rede `/27`?
```text
2^(32 - 27) - 2 = 30 hosts
```

---

## 🔐 Endereços IP Reservados

| Faixa               | Descrição             |
|---------------------|------------------------|
| 10.0.0.0/8          | Rede privada (A)       |
| 172.16.0.0/12       | Rede privada (B)       |
| 192.168.0.0/16      | Rede privada (C)       |
| 127.0.0.0/8         | Loopback               |
| 169.254.0.0/16      | Link-local             |
| 224.0.0.0/4         | Multicast              |

---

## 🔎 Ferramentas de apoio

- `ipcalc` — cálculo de sub-redes:
```bash
ipcalc 192.168.1.0/26
```

- `nmap` — descoberta de hosts ativos:
```bash
nmap -sn 192.168.1.0/24
```

- `whois`, `traceroute`, `ping` — verificação e rastreio de redes

---

## 🧠 Resumo

- IPs são divididos em rede + host.
- Subnetting permite dividir redes maiores em blocos menores.
- CIDR substitui o antigo modelo de classes.
- IPs privados não são roteáveis na internet pública.

---

## 🔗 Referências

- [RFC 1918 - IP Address Allocation for Private Internets](https://datatracker.ietf.org/doc/html/rfc1918)
- [IANA IPv4 Special-Purpose Address Registry](https://www.iana.org/assignments/iana-ipv4-special-registry/iana-ipv4-special-registry.xhtml)
- [Subnetting Practice](https://subnettingpractice.com/)

---

Este conteúdo faz parte da [pasta de redes](../networks/) do repositório [`study`](attachs/docs/README.md).

