# 📊 AWS Budgets: Configuração de Orçamento e Alertas

## 📌 Visão Geral

O **AWS Budgets** permite que você configure alertas com base em uso e gastos dentro da conta da AWS. É ideal para:
- **Evitar surpresas na fatura**
- **Controlar o uso dentro do Free Tier**
- **Receber notificações proativas por e-mail ou via SNS**

---

## 🛡️ Habilitando Acesso ao Billing para Usuários IAM

Por padrão, apenas o usuário **root** tem acesso ao console de Billing. Para permitir que usuários IAM vejam informações de faturamento:

1. Acesse o console da AWS com o usuário root.
2. Vá em:  
   **Billing Dashboard > Account Settings**
3. Habilite a opção:  
   ✅ **IAM User and Role Access to Billing Information**
4. Clique em **Save changes**.

🔐 Após isso, associe políticas de permissão aos usuários IAM (como `AWSBillingReadOnlyAccess` ou `AWSBudgetsFullAccess`).

---

## 📦 Acompanhando o Free Tier

1. No console da AWS, acesse:  
   **Billing > Free Tier**
2. Verifique:
   - Uso atual de cada serviço.
   - Limite gratuito restante.
   - Serviços que **ultrapassaram** o Free Tier.

---

## 💰 Criando um Orçamento (Budget)

### 🔧 Etapas Práticas

1. Acesse o console:  
   [https://console.aws.amazon.com/billing/home#/budgets](https://console.aws.amazon.com/billing/home#/budgets)

2. Clique em **Create budget**.

3. Escolha o tipo:
   - **Cost budget**: baseado no valor gasto.
   - **Usage budget**: baseado em quantidade de uso (ex: horas EC2).
   - **Reservation budget / Savings Plans**: para controle de descontos por compromisso.

4. Defina:
   - Nome do budget: `OrçamentoMensalAWS`
   - Tipo de período: `Monthly`
   - Valor limite: `R$ 20,00` (exemplo)

5. Em **Thresholds and alerts**, configure:
   - Enviar alerta quando custo **real** ≥ 80% do budget.
   - Enviar alerta quando custo **estimado** ≥ 100% do budget.
   - Informe um **e-mail válido**.

6. (Opcional) Configure ações automáticas via **SNS** ou **AWS Lambda**.

7. Clique em **Create budget**.

---

## ✉️ Recebendo Notificações

Você receberá alertas no e-mail cadastrado com:
- Percentual atingido
- Valor atual e valor estimado
- Serviço que mais consome recursos

---

## 🧪 Teste Prático

1. Gere algum uso na conta (ex: iniciar EC2 t2.micro ou criar bucket no S3).
2. Acompanhe o crescimento do uso no **Free Tier dashboard**.
3. Simule um orçamento baixo (ex: R$ 1,00) para forçar alerta rápido.
4. Aguarde o e-mail de notificação para validar o processo.

---

## 🛡️ Política Exemplo para Acesso Total ao Billing

> Use com cautela. Ideal apenas para administradores.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "budgets:*",
        "ce:*",
        "cur:*",
        "aws-portal:*"
      ],
      "Resource": "*"
    }
  ]
}
