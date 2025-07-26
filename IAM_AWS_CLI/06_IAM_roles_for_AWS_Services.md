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
🔸 Política Anexada
Nome da política: IAMReadOnlyAccess

Tipo: Gerenciada pela AWS

Função: Permite acesso de leitura a recursos IAM.

### 3. Tags (opcional)
Nenhuma tag adicionada neste exemplo, mas boas práticas recomendam usar tags como:

text
Copiar
Editar
Environment: dev
Owner: Adriano
Projeto: AWS Architect Study
✅ Validação e Boas Práticas
🚨 Observação:
Durante o hands-on, a role foi criada utilizando o usuário root, o que não é uma boa prática.

✅ Boas Práticas:
Evitar uso do usuário root. Sempre criar um usuário IAM com permissões administrativas para essas operações.

Adotar tags para melhor gerenciamento.

Atribuir o mínimo necessário de permissões (principle of least privilege).

Verificar se a role está realmente sendo assumida pela instância EC2, utilizando curl 169.254.169.254/latest/meta-data/iam/security-credentials/ dentro da EC2.

📚 Referências
IAM Roles - AWS Docs

IAM Role Trust Relationships

