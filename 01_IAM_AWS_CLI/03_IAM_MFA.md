# 🔐 IAM - Multi-Factor Authentication (MFA)

## 📌 Visão Geral

O **MFA (Multi-Factor Authentication)** é uma camada adicional de segurança que exige dois fatores para autenticação: algo que o usuário **sabe** (senha) e algo que o usuário **possui** (dispositivo gerador de código).  
Na AWS, é altamente recomendado ativar MFA para todos os usuários IAM e especialmente para a **conta root**.

---

## 🎯 Objetivos do Estudo

- Compreender o conceito de MFA no contexto da AWS.
- Ativar MFA para usuários IAM e conta root.
- Praticar o processo completo de configuração via Console AWS.
- Aprender boas práticas de segurança relacionadas ao uso de MFA.

---

## 📚 Conceitos Importantes

| Termo                     | Descrição                                                                 |
|--------------------------|--------------------------------------------------------------------------|
| **MFA**                  | Multi-Factor Authentication – autenticação com dois ou mais fatores.     |
| **TOTP**                 | Time-Based One-Time Password – código temporário gerado a cada 30s.      |
| **Dispositivo Virtual**  | App autenticador como Google Authenticator, Authy ou AWS Virtual MFA.    |
| **MFA Físico**           | Dispositivos físicos como chaves YubiKey ou cartões de segurança.        |

---

## 🛠️ Passo a Passo – Ativando o MFA (Hands-On)

### ✅ 1. Acesse o Console da AWS
- Entre como usuário IAM ou root.

### ✅ 2. Vá até **IAM → Users**
- Selecione o usuário desejado.

### ✅ 3. Acesse a aba **Security credentials**
- Encontre a seção "Assigned MFA device".
- Clique em **Manage**.

### ✅ 4. Escolha o tipo de dispositivo MFA
- Selecione **Virtual MFA device** (ex: Google Authenticator).

### ✅ 5. Configure no aplicativo autenticador
- Escaneie o QR code no app autenticador.
- Digite dois códigos consecutivos gerados para validar.

### ✅ 6. Conclua a ativação
- O status do MFA aparecerá como **"Assigned"** para o usuário.

---

## 📸 Capturas de Tela (sugestão)

> Para enriquecer a documentação:
> - QR Code sendo escaneado
> - Confirmação de ativação
> - Tela de login com solicitação do código MFA

---

## ⚠️ Boas Práticas

- **Ative MFA imediatamente** na conta root.
- Exija MFA para todos os usuários com permissões elevadas.
- Crie políticas para restringir ações sem MFA.
- Evite depender apenas de usuário/senha para segurança.

---

## 🔐 Exemplo MFA via AWS CLI (avançado)

```bash
aws sts get-session-token \
  --serial-number arn:aws:iam::123456789012:mfa/nome-do-usuario \
  --token-code 123456
```

> O comando acima gera credenciais temporárias após autenticação com MFA.

---

## 📖 Referências

- [Documentação oficial AWS IAM MFA](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html)
- Curso: **AWS Certified Solutions Architect - SAA-C03** (Udemy)
- Estudo realizado em: **26/07/2025**

---

## ✅ Status do Módulo

📂 **IAM_MFA**  
📅 Estudo concluído e documentado  
🔐 MFA aplicado com sucesso na conta de testes AWS

---