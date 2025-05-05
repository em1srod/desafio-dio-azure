# Criação de Máquina Virtual no Microsoft Azure

Este resumo orienta o processo de criação e configuração de uma máquina virtual (VM) usando o portal do Microsoft Azure. Também apresenta conceitos importantes e boas práticas para cada etapa.

---

## 🖥️ O que é uma Máquina Virtual?

Uma máquina virtual (VM) é um ambiente computacional emulado que roda em um hardware físico real. No Azure, é possível criar VMs de diversos tipos (Windows, Linux) e usá-las para hospedagem, desenvolvimento, testes ou produção.

---

## 🚀 Passo a Passo — Criando uma VM no Azure

### 1. Acesse o Portal
- Vá para: [https://portal.azure.com](https://portal.azure.com)
- Faça login com sua conta Microsoft.

---

### 2. Inicie a criação da VM
- No menu lateral, clique em **"Máquinas virtuais"**.
- Clique no botão **“+ Criar” > “Máquina Virtual do Azure”**.

---

### 3. Configure a guia "Básico"
Preencha os campos obrigatórios:

| Campo                  | Descrição                                               |
|------------------------|----------------------------------------------------------|
| **Assinatura**         | Escolha a assinatura ativa                              |
| **Grupo de Recursos**  | Use um existente ou crie um novo (ex: `rg-demo`)        |
| **Nome da VM**         | Nome identificador da sua máquina (ex: `vm-exemplo`)    |
| **Região**             | Localização do datacenter (ex: `Brazil South`)          |
| **Imagem**             | Sistema Operacional (Windows 11, Ubuntu 22.04, etc.)    |
| **Tamanho da VM**      | Capacidade de CPU/RAM. Para testes, use algo como `B1s` |
| **Usuário/Senha ou chave SSH** | Dados de acesso à VM |

---

### 4. Configuração da Porta de Acesso
- Escolha abrir portas como:
  - **3389 (RDP)** para Windows
  - **22 (SSH)** para Linux
- Configure regras de firewall para permitir esses acessos.

---

### 5. Guia "Disco"
- Escolha o tipo de disco (SSD padrão, SSD Premium, HDD).
- Para testes, o SSD padrão é suficiente.

---

### 6. Guia "Rede"
- Será criado automaticamente um VNet, Sub-rede e IP público.
- Pode manter as configurações padrão para fins de aprendizado.

---

### 7. Revisar e Criar
- Vá até a aba “Revisar + Criar”
- Verifique todos os campos
- Clique em **“Criar”**. O Azure irá provisionar a VM em minutos.

---

## 🔐 Conectando à VM

- **Windows**: Baixe o arquivo RDP e conecte com usuário/senha.
- **Linux**: Use o terminal com SSH:
  ```bash
  ssh usuario@ip-publico
