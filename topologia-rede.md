# 🌐 Estrutura da Rede e Infraestrutura

Esta página detalha a montagem física do Rack Central da Link Paraíso, incluindo o sistema de refrigeração automatizado e a organização dos equipamentos.

## 🗄️ Detalhes do Rack
O rack foi projetado para garantir estabilidade térmica e organização dos ativos de rede.

### 🌬️ Sistema de Refrigeração Automatizado
Diferente de racks comuns, este projeto conta com um sistema inteligente de controle de temperatura:
* **Sensores:** Um sensor térmico monitora o ar interno constantemente.
* **Gatilho:** Configurado para ativar ao atingir **31°C**.
* **Atuadores:** Fonte de 12V que alimenta **5 ventoinhas (fans)** de alto fluxo.
* **Objetivo:** Garantir que o calor acumulado pelos switches e servidores não reduza a vida útil do hardware.

### 🔌 Hardware e Conectividade
* **Distribuição:** Switches organizados para facilitar o cabeamento estruturado.
* **Alimentação:** Sistema de proteção contra surtos e distribuição de energia para os fans de 12V.
* **Monitoramento:** Visor digital para acompanhamento em tempo real da temperatura.

## 📍 Topologia Lógica
*(Aqui você pode adicionar detalhes sobre como os IPs são distribuídos na sua rede)*

---
### 🛠️ Manutenção do Rack
1. **Limpeza Mensal:** Verificar acúmulo de poeira nos 4 fans.
2. **Teste do Sensor:** Verificar se o acionamento permanece preciso nos 31°C.
3. **Organização:** Manter cabos identificados para facilitar o suporte remoto.

[⬅ Voltar para a Home](./README.md)
