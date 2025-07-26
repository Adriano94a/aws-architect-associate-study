# 🔐 IAM Security Tools - Estudo e Hands-On

## 🧠 Visão Geral

A AWS oferece ferramentas de segurança dentro do IAM para ajudar na **auditoria**, **monitoramento de acesso** e **implementação do princípio de menor privilégio**. Neste módulo, foram exploradas duas ferramentas fundamentais:

- 📄 **Credentials Report (Relatório de Credenciais)**
- 👁️ **IAM Access Advisor (Conselheiro de Acesso)**

---

## 📄 Credentials Report (Relatório de Credenciais)

### ✅ O que é?

É um relatório gerado em nível de conta, disponível para download no IAM, que lista o **status de segurança das credenciais de todos os usuários da conta**.

### 📋 Informações disponíveis:

- Nome do usuário
- Se possui senha ativada
- Data da última alteração de senha
- Uso de MFA
- Presença de chaves de acesso (Access Keys)
- Data da última utilização das chaves
- Senha vencida ou inativa

### 💡 Utilização:

- Auditoria de **boas práticas de segurança**
- Identificação de usuários inativos ou com MFA desativado
- Revisão do uso de Access Keys

---

## 👁️ IAM Access Advisor (Conselheiro de Acesso)

### ✅ O que é?

Ferramenta em nível de **usuário IAM** que mostra **quais serviços da AWS foram acessados recentemente** por aquele usuário e quando.

### 📋 Informações úteis:

- Serviços com permissão concedida
- Última data de acesso
- Serviços nunca utilizados, mesmo com permissão

### 🔍 Aplicações:

- Aplicar o **princípio de menor privilégio** (removendo acessos desnecessários)
- **Revisão periódica de permissões**
- Base para criação de políticas personalizadas com base no uso real

---

## 🛡️ Princípio do Menor Privilégio

Ambas as ferramentas ajudam a implementar o **Princípio do Menor Privilégio**, que diz:

> "Um usuário, grupo ou serviço só deve ter as permissões mínimas necessárias para realizar seu trabalho."

---

## 🧪 Hands-On Realizado

- Acesso ao painel IAM
- Geração e download do **Credentials Report**
- Acesso ao perfil de um usuário fictício e verificação via **IAM Access Advisor**
- Identificação de serviços não utilizados
- Análise de possíveis excessos de permissões

---

## 🧭 Boas Práticas

- 📉 Revogar acessos não utilizados com base no Access Advisor
- 🔐 Exigir MFA para todos os usuários com acesso ao console
- ⏳ Rotacionar Access Keys regularmente
- 🧹 Remover usuários inativos
- 🧾 Utilizar o Credentials Report periodicamente para auditorias internas

---

## 📚 Referências

- [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- [AWS Access Advisor](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_access-advisor.html)
- [AWS Credential Reports](https://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html)

---

