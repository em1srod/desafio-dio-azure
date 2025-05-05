# Configuração de Instância de Banco de Dados no Microsoft Azure

A computação em nuvem oferece soluções ágeis e escaláveis para hospedagem de bancos de dados, eliminando a necessidade de instalação física e manutenção de servidores locais. O **Azure SQL Database**, serviço PaaS da Microsoft, permite criar instâncias de banco de dados altamente disponíveis, seguras e gerenciadas com poucos cliques.

---

## 🧠 O que é o Azure SQL Database?

O **Azure SQL Database** é um serviço de banco de dados relacional na nuvem, baseado no SQL Server. Ele fornece um ambiente gerenciado que cuida automaticamente de:
- Aplicação de patches
- Backup automático
- Alta disponibilidade
- Escalabilidade sob demanda

Este serviço se enquadra no modelo **DBaaS (Database as a Service)**, permitindo que você foque na lógica da aplicação enquanto o Azure cuida da infraestrutura.

---

## 🚀 Passo a Passo da Configuração

### 1. Acesso ao Portal
Acesse o portal do Azure:
👉 [https://portal.azure.com](https://portal.azure.com)  
Faça login com sua conta Microsoft.

---

### 2. Criação do Banco de Dados SQL

No painel do portal:
- Procure por **"SQL Database"** na barra de pesquisa
- Clique em **“+ Criar”**

---

### 3. Guia Básico – Preenchimento de Informações

| Campo | Descrição |
|-------|-----------|
| **Assinatura** | Selecione sua assinatura do Azure |
| **Grupo de Recursos** | Crie ou selecione um grupo lógico para os recursos |
| **Nome do Banco** | Nome amigável para identificar seu banco (ex: `bd-vendas`) |
| **Servidor SQL** | Crie um novo servidor com login e senha ou reutilize um existente |

> 🔑 O servidor SQL é o ponto de acesso para conexões e fica no formato:
> `seudbserver.database.windows.net`

---

### 4. Configurações de Computação e Armazenamento

- **Modelo de compra**: escolha entre DTU (simplificado) ou vCore (mais controle)
- **Camada de serviço**:
  - **Basic**: para testes e pequenos bancos
  - **Standard**: para uso geral
  - **Premium**: para desempenho alto e missão crítica
- **Espaço de armazenamento**: defina conforme a necessidade do projeto

---

### 5. Regras de Firewall e Segurança

Após criar o servidor, defina quais IPs podem se conectar ao banco:
- Você pode clicar em **“+ Adicionar meu IP”** para permitir o acesso imediato
- Configure autenticação por **login/senha SQL** ou **Azure Active Directory**

---

### 6. Monitoramento e Backup

- Ative **logs de diagnóstico** e **auditoria**
- Configure alertas personalizados via **Azure Monitor**
- Backups são realizados automaticamente e podem ser retidos por até 35 dias (em planos padrão)

---

## 🔗 Conexão ao Banco de Dados

### A. Por SQL Server Management Studio (SSMS)

1. Abra o SSMS
2. Em **Server name**, use:
   ```
   seuservidor.database.windows.net
   ```
3. Autenticação: escolha `SQL Server Authentication`
4. Insira o usuário e senha configurados
5. Clique em **Connect**

> Caso não consiga se conectar, verifique se seu IP está liberado nas configurações de firewall do Azure.

---

### B. Por Aplicações (String de Conexão)

Na página do banco, você encontrará strings de conexão prontas para:
- .NET (ADO.NET)
- JDBC (Java)
- PHP
- ODBC

#### Exemplo genérico (ADO.NET):

```text
Server=tcp:seudbserver.database.windows.net,1433;
Initial Catalog=meubanco;
Persist Security Info=False;
User ID=meuusuario;
Password=minhasenha;
Encrypt=True;
TrustServerCertificate=False;
Connection Timeout=30;
```

---

## 🔐 Boas Práticas

- Use **Azure Key Vault** para armazenar credenciais de forma segura
- Crie **regras de firewall específicas**, evitando liberar IPs amplamente
- Utilize **nomenclaturas padronizadas** para facilitar a gestão
- Ative **auditoria, mascaramento de dados e alertas de desempenho**
- Prefira **camadas de serviço escaláveis**, como o modelo `vCore`, para produção

---

## ✅ Conclusão

A criação de uma instância de banco de dados no Azure é um processo simples, seguro e flexível. Utilizando o **Azure SQL Database**, você garante disponibilidade, escalabilidade e segurança desde o início, com integração fácil a aplicações web, APIs e sistemas corporativos.

Esse processo é essencial para desenvolvedores e administradores de dados que desejam construir soluções modernas na nuvem com agilidade e confiabilidade.
