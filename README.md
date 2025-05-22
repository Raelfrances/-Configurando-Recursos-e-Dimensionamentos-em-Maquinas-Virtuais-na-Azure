# ☁️ Configurando Recursos e Dimensionamento em Máquinas Virtuais na Azure  

## 📌 Objetivo  
Este laboratório tem como objetivo **ensinar a configuração de recursos** e **dimensionamento** de máquinas virtuais (VMs) na plataforma **Microsoft Azure**, garantindo **desempenho eficiente, escalabilidade e otimização de custos**.  

---

## 📝 O que você vai aprender?  
✅ Criar uma **Máquina Virtual** na Azure  
✅ **Configurar CPU, memória, disco e rede** conforme necessidades  
✅ Implementar **Auto Scaling** para escalabilidade automática  
✅ Monitorar e otimizar **uso de recursos** para melhor desempenho  
✅ Gerenciar **custos e eficiência** no consumo de VM  

---

## 🔗 Links úteis  
- 🔹 [Portal do Azure](https://portal.azure.com/)  
- 🔹 [Azure Virtual Machines](https://learn.microsoft.com/pt-br/azure/virtual-machines/)  
- 🔹 [Dimensionamento de VMs](https://learn.microsoft.com/pt-br/azure/virtual-machines/sizes/)  
- 🔹 [Azure Monitor](https://learn.microsoft.com/pt-br/azure/azure-monitor/)  

---

🚀 Passo a Passo: Configuração de Recursos e Dimensionamento
📌 1️⃣ Criando uma VM na Azure
Acesse o portal do Azure e faça login.

Navegue até "Máquinas Virtuais" e clique em Criar.

Escolha as configurações da VM:

📌 Sistema operacional (Linux/Windows)

🔧 Tamanho da VM (CPU, RAM)

💾 Armazenamento e rede

🔐 Definições de segurança

Configure a conexão remota:

Para Linux: Habilite SSH

Para Windows: Habilite RDP

Crie e inicie a VM! 🎉

📌 2️⃣ Configuração de Dimensionamento e Auto Scaling
Para garantir eficiência no consumo de recursos, configure Auto Scaling para sua VM:

---

💻 Criando Auto Scaling via Azure CLI

```Plaintext
bash
az vm scale-set create \
  --name MeuScaleSet \
  --resource-group MeuGrupoAzure \
  --image UbuntuLTS \
  --instance-count 2 \
  --upgrade-policy-mode automatic
📈 Configurando políticas de escala automática
bash
az monitor autoscale create \
  --resource-group MeuGrupoAzure \
  --name MeuAutoScaling \
  --target-resource MeuScaleSet \
  --min-count 1 \
  --max-count 5 \
  --default-count 2 \
  --scale-out-cpu-threshold 75
Este comando configura o Auto Scaling para aumentar ou reduzir a quantidade de instâncias conforme o uso de CPU, garantindo melhor desempenho sem desperdício de recursos.
```
---

📌 3️⃣ Monitoramento e Gerenciamento da VM
Após configurar sua VM e Auto Scaling, utilize Azure Monitor para acompanhar métricas e alertas:
````
🔹 Verificar status da VM:

bash
az vm show --name MinhaVM --resource-group MeuGrupoAzure
🔹 Listar métricas de uso:

bash
az monitor metrics list \
  --resource MinhaVM \
  --metrics "Percentage CPU"
🔹 Parar VM para economia de recursos:

bash
az vm stop --name MinhaVM --resource-group MeuGrupoAzure
````
---
🤝 Contribuições
Se quiser aprimorar este laboratório, adicionar automações ou compartilhar melhorias, sinta-se à vontade para abrir um Pull Request! 💙
