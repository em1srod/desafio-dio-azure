# Identidade, Acesso e Segurança no Microsoft Azure

Este resumo aborda os principais conceitos e serviços relacionados à identidade, autenticação, autorização e segurança no Azure, de acordo com os tópicos do exame AZ-900.

---

## 🔐 Microsoft Entra ID (antigo Azure AD)

O **Microsoft Entra ID** é o serviço de gerenciamento de identidades e acesso baseado em nuvem do Azure.

### Principais funcionalidades:
- **Autenticação** de usuários e serviços
- **SSO (Single Sign-On)**: login único para múltiplas aplicações
- **Gerenciamento de dispositivos**
- **Integração B2B e B2C** (identidades externas)
- **Gerenciamento de aplicações e acessos**

---

## 🌐 Microsoft Entra Domain Services

Permite o uso de serviços de domínio baseados em nuvem **sem gerenciar controladores de domínio**.

### Usos comuns:
- Executar aplicações legadas que não suportam autenticação moderna
- Sincronizar automaticamente identidades do Microsoft Entra ID
- Permitir login em máquinas virtuais com autenticação integrada

---

## 🔑 Autenticação x Autorização

| Conceito       | Definição                                                                 |
|----------------|--------------------------------------------------------------------------|
| **Autenticação** | Processo de verificação da identidade de um usuário ou serviço.         |
| **Autorização**  | Processo que define **o que** o usuário autenticado pode acessar ou fazer. |

---

## 🔁 Autenticação Multifator (MFA)

O MFA aumenta a segurança exigindo **dois ou mais fatores** para autenticação:

- 🔐 Algo que você sabe (senha)
- 📱 Algo que você possui (celular, token)
- 🧬 Algo que você é (biometria)

---

## 👥 Identidades Externas e Acesso B2B/B2C

- **B2B (Business to Business)**: colaboração com usuários de fora da organização
- **B2C (Business to Consumer)**: autenticação de usuários finais em aplicações públicas

Esses recursos permitem gerenciar identidades externas com segurança e controle.

---

## ⚙️ Acesso Condicional

Permite aplicar **políticas baseadas em sinais contextuais** como:

- Localização do IP
- Dispositivo usado
- Aplicativo acessado
- Detecção de risco

📌 Exemplo: “Exigir MFA apenas fora da rede corporativa”.

---

## 🧱 Controle de Acesso Baseado em Função (RBAC)

Sistema de controle granular que permite:

- Conceder **apenas as permissões necessárias** por função
- Restringir ações no portal do Azure
- Definir papéis como:
  - Leitor
  - Colaborador
  - Administrador

---

## 🔒 Modelo de Confiança Zero

**Zero Trust (Confiança Zero)** é uma abordagem de segurança que parte do princípio:  
> “Nunca confie, sempre verifique.”

Isso significa que nenhuma solicitação de acesso é confiável por padrão — mesmo que venha de dentro da rede.

---

## 🛡️ Defesa em Profundidade

Modelo de segurança baseado em **camadas**, no qual:

- Cada camada protege a anterior
- Reduz o impacto de invasões parciais
- Inclui segurança de rede, identidade, dados e aplicações

---

## 🧪 Microsoft Defender para Nuvem

Serviço de monitoramento de segurança que:

- Fornece **recomendações proativas**
- **Detecta malware** e ameaças
- **Antecipa ataques** com inteligência de segurança
- Garante acesso just-in-time a portas de VM

---

## ✅ Conclusão

A segurança no Azure é baseada em uma estrutura robusta que combina identidade, controle de acesso, autenticação multifator, regras condicionais e monitoramento constante. Compreender esses serviços é fundamental para operar com segurança na nuvem.
