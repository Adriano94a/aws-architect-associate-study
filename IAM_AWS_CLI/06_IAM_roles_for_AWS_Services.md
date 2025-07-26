# IAM Roles for AWS Services + Hands-On

## 🌐 Visão Geral

O IAM Role (Função do IAM) é uma identidade que pode ser assumida por serviços da AWS, usuários ou outras contas. Ao invés de conceder permissões diretamente a recursos (como EC2, Lambda, etc.), criamos funções com políticas associadas que definem o que essas entidades podem ou não fazer.

## 🎯 Objetivo do Hands-On

Criar uma função chamada `DemoRoleForEC2` que permita que uma instância EC2 acesse serviços da AWS em nome do usuário.

---

## 🛠️ Etapas Práticas

### 1. Criando a Role no IAM

#### 🔸 Nome
- **Nome da Role:** `DemoRoleForEC2`
- **Descrição:** `Allows EC2 instances to call AWS services on your behalf.`

#### 🔸 Entidade Confiável
Selecionada a entidade confiável: **Serviço EC2**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "ec2.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}


### 2. Permissões

#### 🔸 Política Anexada

- **Nome da política:** `IAMReadOnlyAccess`
- **Tipo:** Gerenciada pela AWS
- **Função:** Permite acesso de leitura a recursos IAM.

---

### 3. Tags (opcional)

Nenhuma tag adicionada neste exemplo, mas boas práticas recomendam usar tags como:

```text
Environment: dev
Owner: Adriano
Projeto: AWS Architect Study
