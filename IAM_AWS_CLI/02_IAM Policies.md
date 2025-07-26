# IAM Policies – Visão Geral

## O que são Políticas IAM?

As políticas do IAM são documentos JSON que definem permissões para usuários, grupos e roles. Elas especificam quais ações são permitidas ou negadas em quais recursos da AWS.

---

## Tipos de Políticas

- **Gerenciadas pela AWS:** Políticas padrão criadas e mantidas pela AWS.
- **Gerenciadas pelo cliente:** Políticas criadas por você para atender necessidades específicas.
- **Inline:** Políticas anexadas diretamente a um usuário, grupo ou role, específicas para aquele recurso.

---

## Estrutura Básica de uma Política JSON

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::example_bucket"
    }
  ]
}
