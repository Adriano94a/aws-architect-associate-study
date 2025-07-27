# 🖥️ AWS CloudShell – Terminal Web da AWS

## 📌 Visão Geral

O **AWS CloudShell** é um terminal interativo baseado em navegador que permite executar comandos do AWS CLI diretamente no console da AWS, sem necessidade de instalação local.

Ele vem pré-configurado com a CLI, SDKs e ferramentas úteis, além de permitir upload e download de arquivos.

---

## 🎯 Objetivos do Estudo

- Entender o funcionamento e as vantagens do AWS CloudShell.
- Saber quando usá-lo no lugar da CLI local.
- Conhecer limitações e boas práticas.
- Verificar a disponibilidade por regiões.

---

## 🌐 Region Availability

O CloudShell **não está disponível em todas as regiões** da AWS.  
Você pode ver a lista atualizada em:  
🔗 [CloudShell Availability – AWS Docs](https://docs.aws.amazon.com/general/latest/gr/cloudshell.html)

### Regiões com suporte (em 2025):

| Região                    | Código da Região   |
|---------------------------|--------------------|
| US East (N. Virginia)     | `us-east-1`        |
| US West (Oregon)          | `us-west-2`        |
| Europe (Ireland)          | `eu-west-1`        |
| South America (São Paulo)| `sa-east-1`        |
| Asia Pacific (Singapore) | `ap-southeast-1`   |
| ...                      | ...                |

⚠️ Se uma região **não suporta o CloudShell**, um aviso será exibido ao tentar acessá-lo.

---

## 🛠️ Como Acessar e Usar

### ✅ 1. Acesse o Console AWS

- Faça login no Console AWS com seu usuário IAM.

### ✅ 2. Clique no ícone do **CloudShell** (terminal)

- Localizado no canto superior direito do console (ícone de prompt).

### ✅ 3. Aguarde a inicialização

- Um container temporário será iniciado automaticamente.
- Você pode começar a executar comandos AWS CLI, Bash, etc.

---

## ⚙️ Funcionalidades

| Recurso                         | Descrição                                                                 |
|----------------------------------|--------------------------------------------------------------------------|
| AWS CLI pré-instalado           | `aws --version` já disponível.                                           |
| Sessão persistente por região   | Seus arquivos são salvos por região.                                     |
| Upload e download               | Envie arquivos para o terminal ou baixe arquivos com botões dedicados.   |
| Armazenamento                   | 1 GB de armazenamento persistente (por região).                          |

---

## 🤖 Exemplos de Comandos

```bash
aws s3 ls
aws ec2 describe-instances
echo "Hello CloudShell" > hello.txt
```

---

## ⚠️ Limitações e Considerações

- Cada região tem **1 GB de armazenamento persistente**.
- O tempo de **inatividade encerra a sessão** automaticamente.
- Apenas **usuários com permissões IAM** adequadas podem usar o CloudShell.
- Pode não ser o ideal para **automação contínua** (use EC2 ou Lambda).

---

## 🛡️ Segurança

- CloudShell usa credenciais temporárias do usuário logado.
- MFA e políticas IAM são aplicáveis normalmente.
- Ideal para tarefas rápidas e seguras diretamente via browser.

---

## 📖 Referências

- [AWS CloudShell Documentation](https://docs.aws.amazon.com/cloudshell/latest/userguide/)
- Curso: **AWS Certified Solutions Architect - SAA-C03** (Udemy)
- Estudo realizado em: **26/07/2025**

---

## ✅ Status do Módulo

📂 **AWS_CloudShell**  
📅 Estudo concluído e validado com testes em múltiplas regiões  
🌎 Regiões com suporte identificadas e mapeadas  

---