# ⚙️ AWS CLI - Setup, Access Keys e Hands-On

## 📌 Visão Geral

O **AWS CLI (Command Line Interface)** é uma ferramenta que permite gerenciar serviços AWS via terminal, oferecendo automação e controle direto dos recursos. É amplamente usada em ambientes DevOps, scripts, e integrações com SDKs.

Este módulo documenta o processo de:
- Geração e uso de Access Keys (chaves de acesso)
- Instalação e configuração do AWS CLI no Windows
- Primeiros comandos práticos (Hands-On)

---

## 🎯 Objetivos do Estudo

- Entender o que são Access Keys e sua finalidade.
- Aprender a instalar e configurar o AWS CLI no Windows.
- Executar comandos básicos para validar o funcionamento da CLI.
- Fortalecer a segurança ao manipular chaves de acesso.

---

## 🔑 O que são Access Keys?

Access Keys consistem em:
- **Access Key ID**
- **Secret Access Key**

Elas permitem acesso programático via CLI, SDKs ou ferramentas como Terraform.

⚠️ **Nunca compartilhe ou suba suas chaves em repositórios públicos.**  
Use variáveis de ambiente, arquivos seguros ou serviços como AWS Secrets Manager.

---

## 🖥️ Instalação do AWS CLI no Windows

### ✅ 1. Baixar o instalador

- Acesse: [https://aws.amazon.com/cli/](https://aws.amazon.com/cli/)
- Baixe o instalador para Windows (versão 2.x recomendada).

### ✅ 2. Executar o instalador

- Avance com as etapas padrão.
- Verifique a instalação com:

```powershell
aws --version
```

Exemplo de saída esperada:
```bash
aws-cli/2.16.3 Python/3.11.6 Windows/10 exe/AMD64
```

---

## 🔧 Configuração do AWS CLI

### ✅ 1. Gerar Access Keys no IAM

- Console AWS → **IAM → Users → Security credentials**
- Clique em **Create access key**
- Copie a **Access Key ID** e a **Secret Access Key**

### ✅ 2. Executar comando `aws configure`

No terminal:

```bash
aws configure
```

Preencha com:

```
AWS Access Key ID:     SUA_ACCESS_KEY
AWS Secret Access Key: SUA_SECRET_KEY
Default region name:   us-east-1
Default output format: json
```

Essas informações são salvas em:
- `~/.aws/credentials`
- `~/.aws/config`

---

## 🤖 Comandos Básicos - Hands-On

### ✅ Listar buckets S3

```bash
aws s3 ls
```

### ✅ Verificar identidade atual

```bash
aws sts get-caller-identity
```

### ✅ Verificar arquivos de configuração

```bash
cat ~/.aws/config
cat ~/.aws/credentials
```

---

## ⚠️ Boas Práticas com Access Keys

- Use **usuários IAM específicos** com permissões mínimas necessárias.
- Nunca ative Access Keys para a conta root.
- **Revogue chaves antigas** ou não utilizadas.
- Use MFA sempre que possível para maior proteção.

---

## 📖 Referências

- [Documentação oficial AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/)
- Curso: **AWS Certified Solutions Architect - SAA-C03** (Udemy)
- Estudo realizado em: **semana de 21 a 26/07/2025**

---

## ✅ Status do Módulo

📂 **AWS_CLI_SETUP**  
📅 Estudo concluído e testado localmente  
💡 AWS CLI funcional no ambiente Windows

---