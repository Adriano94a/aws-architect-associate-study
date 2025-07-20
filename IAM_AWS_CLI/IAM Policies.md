# IAM Policies

As IAM Policies (Políticas de Gerenciamento de Identidade e Acesso) são documentos em formato JSON que definem permissões concedidas a usuários, grupos ou roles na AWS. Elas controlam o que pode ou não ser feito com recursos específicos.

---

## 📌 Conceitos Fundamentais

- **Políticas em nível de grupo**: 
  Aplicadas a um grupo, são herdadas automaticamente por todos os usuários membros.

- **Políticas inline**: 
  Criadas diretamente em um único usuário, grupo ou role. São exclusivas e não reutilizáveis.

- **Usuário em múltiplos grupos**: 
  Um usuário pode herdar permissões de vários grupos simultaneamente, combinando suas políticas.

---

## 📐 Estrutura de uma Policy (JSON)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "ListBucketPolicy",
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::example-bucket"
    }
  ]
}
🧩 Componentes do JSON
Campo	Descrição
Version	Versão da política (use sempre "2012-10-17")
Sid	Identificador opcional da política (Statement ID)
Effect	Define se a ação será permitida (Allow) ou negada (Deny)
Action	Ação(s) específicas que serão controladas
Resource	Recurso(s) afetado(s) pela política
Condition	(Opcional) Regras adicionais para quando a política será aplicada
Principal	Usado em policies baseadas em recursos (ex.: em buckets S3)

✅ Boas Práticas com Policies
Use grupos com políticas gerenciadas sempre que possível.

Prefira políticas gerenciadas pela AWS quando disponíveis.

Restrinja permissões ao mínimo necessário (principle of least privilege).

Evite usar "*" em Action e Resource, principalmente em ambientes de produção.

Use Condition para limitar o escopo de permissões (ex.: por IP, tempo, etc).

📚 Exemplo de Política para S3
json

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:PutObject",
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::meu-bucket/*"
    }
  ]
}
Essa política permite ao usuário fazer upload e download de arquivos no bucket meu-bucket.

🔒 Lembre-se:
Mesmo com permissões Allow, uma política explícita de Deny sempre prevalece.

Policies são cumulativas, ou seja, somam permissões de diferentes fontes (grupos, roles, inline).