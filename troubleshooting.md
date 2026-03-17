# 🧠 Base de Conhecimento (Troubleshooting)

Este guia contém as soluções para os problemas mais comuns identificados na rede Link Paraíso.

---

## 🛑 1. O WinBox não conecta
Se você tentar acessar a RB 3011 e não conseguir:
* **Verifique a Porta:** Lembre-se que a porta foi alterada para `9612`. O endereço deve ser `10.10.10.1:9612`.
* **Port Knocking:** Se o seu IP não estiver na "Rede Suporte", você pode estar bloqueado. Tente pingar o IP da RB antes de abrir o WinBox.
* **Cabo Físico:** Verifique se você está conectado nas portas da `bridge2` (Portas 3, 4 ou 5).

## 📹 2. Câmeras/DVR Offline
Se o acesso remoto às câmeras parar de funcionar:
* **Verificar NAT:** Vá em `/ip firewall nat` e veja se a regra `TS ARENA` ou `Proxy` está habilitada (não pode estar cinza).
* **IP do DVR:** Confirme se o DVR não mudou de IP. Ele deve estar travado em `10.10.10.200`.
* **Link de Internet:** Verifique se a interface `ether1 Link 01 M2` recebeu IP do provedor.

## 🧱 3. Cliente bloqueado por "Malandro" (Portscan)
O firewall automático pode bloquear IPs que tentam acessos indevidos.
* **Sintoma:** O cliente ou você não consegue acessar nada da rede.
* **Solução:** Vá em `/ip firewall address-list`, procure pelo IP na lista `PORTASCAN` e apague a entrada. 
* **Dica:** O bloqueio dura 1 semana se não for removido manualmente.

## ❄️ 4. Superaquecimento do Rack
Se o sensor marcar mais de **31°C** e os fans não ligarem:
* **Fonte 12V:** Verifique se a fonte que alimenta os 4 fans está ligada na tomada.
* **Conector do Sensor:** Veja se os fios do sensor térmico não soltaram do controlador digital.
* **MikroTik:** Use o comando `/system health print` para ver a temperatura interna da RB 3011. Se estiver acima de 50°C, force a ventilação externa.

---

### 🔄 Procedimento de Reset de Emergência
Caso a rede trave completamente:
1. Desligue o disjuntor do Rack.
2. Aguarde 30 segundos (para descarregar os capacitores da RB 3011).
3. Ligue o disjuntor.
4. Aguarde 2 minutos e verifique se o LED da RB 3011 estabilizou.

[⬅ Voltar para a Home](./README.md)
