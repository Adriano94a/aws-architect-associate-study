# 🔐 IAM - Visão Geral e Melhores Práticas de Segurança

## 📘 Introdução ao IAM

O **IAM (Identity and Access Management)** é o serviço da AWS responsável por **gerenciar identidades e controlar acessos** aos recursos da nuvem. Com ele, é possível criar e administrar usuários, grupos, permissões e políticas de segurança de forma granular.

---

## 🛡️ Boas Práticas de Segurança com IAM

A seguir estão as práticas recomendadas para manter sua conta AWS segura e bem gerenciada:

### 1. 🧑‍💼 Use uma Conta Root Apenas para Tarefas Críticas

- **Evite o uso cotidiano da conta root.**
- Utilize a root apenas para ações como: fechamento da conta, alteração de informações de cobrança ou gerenciamento de serviços globais.
- **Proteja a root com MFA.**

### 2. 👥 Crie Usuários IAM Separados

- Crie um usuário IAM para cada pessoa que precisará de acesso à conta.
- **Nunca compartilhe credenciais entre usuários.**
- Evite fornecer suas chaves ou senha a amigos, colegas ou terceiros.

### 3. 🔒 Utilize MFA (Autenticação Multifator)

- Ative o **MFA (Multi-Factor Authentication)** para todos os usuários, especialmente para a conta root.
- MFA adiciona uma camada extra de proteção contra acessos não autorizados.

### 4. 🧠 Aplique o Princípio de Menor Privilégio

- Conceda apenas as permissões **mínimas necessárias** para o usuário executar suas tarefas.
- Use o IAM Access Advisor e o Access Analyzer para identificar permissões excessivas.

### 5. 📁 Use Grupos para Gerenciar Permissões

- Crie **grupos IAM** com políticas definidas por função (ex: DevOps, Financeiro, Suporte).
- Adicione usuários aos grupos ao invés de atribuir políticas diretamente.

### 6. 🔑 Geração e Uso de Chaves de Acesso

- Geração de chaves de acesso (Access Key ID e Secret Access Key) deve ser feita com cautela.
- **Guarde essas chaves em local seguro**. Elas não são recuperáveis depois.
- Prefira o uso de perfis de autenticação ou roles temporárias (STS) em ambientes de produção.
- **Desative ou exclua chaves antigas ou não utilizadas.**

### 7. 🧾 Habilite e Analise o Relatório de Credenciais

- Gere periodicamente o **Credentials Report**.
- Verifique se as chaves e senhas estão em conformidade com as boas práticas (uso recente, MFA ativo, etc).

### 8. 🔐 Crie Políticas com Regras Claras

- Defina regras com base em **ações permitidas**, **recursos específicos** e **condições (como IP ou horário)**.
- Use políticas gerenciadas da AWS quando possível, ou crie políticas customizadas com base no uso real.

### 9. 🌐 Use Duas Contas AWS (Prática Avançada)

- Para projetos mais críticos ou ambientes corporativos, use uma conta principal para **billing e controle financeiro** e outras contas segregadas por ambiente (ex: dev, teste, produção).
- Gerencie o acesso via AWS Organizations.

---

## 📌 Resumo Prático

| Boa Prática                           | Descrição                                                                 |
|--------------------------------------|---------------------------------------------------------------------------|
| Conta Root protegida                 | Usar apenas para ações críticas com MFA ativado                          |
| Usuários individuais                 | Nunca compartilhar credenciais                                            |
| MFA obrigatório                      | Para todos os acessos (console e programático)                           |
| Menor privilégio                     | Permissões mínimas necessárias                                            |
| Uso de grupos                        | Para gerenciar permissões em escala                                      |
| Chaves de acesso                     | Criar com segurança e rotacionar regularmente                            |
| Relatórios e análises               | Usar Credentials Report e Access Advisor para auditoria                  |
| Duas contas (avançado)               | Separação de ambientes e controle financeiro                             |

---

## 🧭 Próximos Estudos Recomendados

- Políticas IAM em JSON (sintaxe e estrutura)
- IAM Roles e Trust Relationships
- IAM Policy Simulator
- AWS Organizations e SCPs (Service Control Policies)

---

## 📚 Referências Oficiais

- [AWS IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
- [Getting Started with IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started.html)
