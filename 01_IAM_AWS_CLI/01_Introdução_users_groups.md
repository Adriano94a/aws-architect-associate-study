# 📘 IAM – Users e Groups (AWS)

## 🌐 Visão Geral

* **IAM (Identity and Access Management)** é um serviço **global** da AWS, ou seja, não está vinculado a uma região específica.
* Sua principal função é **gerenciar identidades e permissões** dentro de uma conta AWS.
* O uso da conta **root (raiz)** não é recomendado para atividades do dia a dia, sendo indicada apenas para ações críticas.

---

## 🔐 Conta Root (Raiz)

* Criada automaticamente no momento do cadastro da AWS.
* Possui **acesso total e irrestrito** a todos os serviços e configurações.
* **Boas práticas:**

  * Ativar **MFA (autenticação multifator)** imediatamente.
  * Utilizar apenas para:

    * Ações críticas como exclusão da conta
    * Configuração de faturas e pagamento
    * Recuperação de permissões

---

## 👤 Criação de Usuários IAM

* Os **usuários IAM** são identidades dentro da conta AWS com permissões controladas.
* Ao criar um usuário, é possível conceder:

  * Acesso ao **console da AWS** (usuário e senha)
  * Acesso programático via **Access Key ID + Secret Access Key**

### 🔗 URL personalizada de login

* É possível gerar uma URL exclusiva para o login IAM:

```
https://<ID_da_conta>.signin.aws.amazon.com/console
```

* O usuário acessa essa URL, insere **nome de usuário + senha** e acessa o console com segurança.

---

## 👥 Grupos IAM

* **Grupos** permitem agrupar usuários com permissões semelhantes.
* **Boa prática:** atribuir permissões ao grupo, e não diretamente ao usuário.

### 🧩 Exemplos comuns de grupos:

| Grupo            | Política Sugerida        | Função                                                   |
| ---------------- | ------------------------ | -------------------------------------------------------- |
| `Administrators` | `AdministratorAccess`    | Acesso total à conta                                     |
| `Developers`     | Custom (EC2, S3, Lambda) | Acesso apenas aos serviços de desenvolvimento            |
| `ViewOnly`       | `ReadOnlyAccess`         | Apenas visualização dos recursos, sem poder modificá-los |

---

## 📄 Políticas (Policies)

* Permissões são concedidas por meio de documentos JSON chamados **políticas**.
* Tipos de políticas:

  * **AWS Managed**: criadas e mantidas pela AWS.
  * **Customer Managed**: personalizadas pelo usuário.
  * **Inline**: anexadas diretamente a um usuário, grupo ou role (menos recomendadas para reuso).

---

## 🛡️ Princípio do Menor Privilégio

> Sempre aplique o princípio do **Least Privilege**:
> conceda apenas as permissões mínimas necessárias para que o usuário execute suas tarefas.

---

## ✅ Checklist de Boas Práticas (IAM)

* [x] Ativar MFA na conta root
* [x] Criar um usuário IAM com permissões de administrador
* [x] Utilizar grupos para gerenciar permissões
* [x] Configurar URL personalizada para login IAM
* [x] Criar alertas de faturamento
* [x] Documentar todas as permissões e políticas aplicadas

---

✍️ *Essas anotações fazem parte do estudo do curso "Ultimate AWS Certified Solutions Architect Associate 2025" com foco na certificação SAA-C03.*
