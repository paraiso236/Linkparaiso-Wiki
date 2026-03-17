# ⚙️ Ativos e Configurações de Rede - Link Paraíso

Este documento detalha a configuração real dos equipamentos, extraída diretamente via terminal (export).

## 📶 Roteador Principal: MikroTik RB 3011
O núcleo da rede, responsável pelo gerenciamento de clientes, segurança e VPN.

* **Modelo:** RB3011UiAS-RM
* **Versão do Sistema:** RouterOS 7.19.4
* **Porta WinBox:** `9612` (Segurança ativada)
* **Porta Web:** `88`

### 🌐 Mapeamento de Portas Físicas
* **WAN (Internet):** `ether1 Link 01 M2` (Principal).
* **LAN (Bancada/Interna):** `bridge2 Rede Interna` (Portas 3, 4 e 5).
* **Distribuição Clientes:** `bridge1 PPPoE` (Portas 8, 9 e SFP1).

### 📋 Endereçamento IP e DHCP
| Rede | Interface | Faixa de IP | Gateway |
| :--- | :--- | :--- | :--- |
| **Rede Interna** | ether4 | `10.10.10.0/24` | `10.10.10.1` |
| **Rede Reserva** | ether5 | `10.0.0.0/24` | `10.0.0.1` |
| **Pool PPPoE** | bridge1 | `172.32.0.2-254`| `172.32.0.1` |
| **VPN WireGuard** | VPNCELL | `10.20.20.0/24` | Porta 51820 |

### 📹 Redirecionamento de Serviços (NAT)
Acessos configurados para serviços externos:
* **TS ARENA:** Porta Externa `4500` -> IP `10.10.10.252` (Porta 3389).
* **Emby Server:** Porta Externa `1993` -> IP `10.10.10.247` (Porta 8096).
* **Proxy/Emby:** Porta `8096` disponível na bridge PPPoE para o IP `10.10.10.250`.

### 🛡️ Segurança e Firewall
* **Proteção PORTASCAN:** IPs que tentam forçar acesso nas portas 21-23, 3389, 53 e 1723 são movidos para a lista de bloqueio automática por 1 semana.
* **Rede Suporte:** Acesso liberado via "Port Knocking" na porta `9612`.
* **FastTrack:** Habilitado para otimizar o processamento e reduzir latência.

---

### 💾 Histórico de Backups
* Arquivo mais recente: `MikroTik-20260316-2343.backup` (Gerado em 16/03/2026).

[⬅ Voltar para a Home](./README.md)
