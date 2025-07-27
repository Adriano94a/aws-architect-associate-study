## 🖥️ Amazon EC2 – Primeira Instância

### ☁️ O que é EC2?

O Amazon EC2 (Elastic Compute Cloud) permite alugar máquinas virtuais (chamadas de instâncias), com escalabilidade e alta disponibilidade.

Você pode:
- Escolher sistema operacional (Linux, Windows, etc.)
- Definir CPU, memória e disco (EBS)
- Configurar scripts de inicialização (Bootstrap)
- Controlar acesso com chaves SSH
- Configurar regras de firewall (Security Groups)

---

### 🧠 Tipos de Instâncias

As instâncias EC2 são categorizadas com base em suas características de uso. Aqui estão alguns exemplos:

| Tipo           | Categoria                 | Descrição                                                                 |
|----------------|---------------------------|---------------------------------------------------------------------------|
| `t2.micro`     | Uso geral (Free Tier)     | Ideal para testes leves, gratuito por 750h/mês                            |
| `t2.xlarge`    | Uso geral                 | Mais vCPUs e memória que o micro                                          |
| `c5d.4xlarge`  | Computação otimizada      | Alta performance de CPU com armazenamento local NVMe                      |
| `r5.16xlarge`  | Memória otimizada         | Altíssimo volume de RAM (ideal para bancos de dados ou cache in-memory)  |
| `m5.8xlarge`   | Balanceada (CPU/Memória)  | Uso geral de larga escala (web servers, bancos, sistemas grandes)        |

---

### ⚙️ Exemplo: Criando uma `t2.micro`

1. Acesse o console AWS e vá para `EC2`.
2. Clique em **"Launch Instance"**.
3. Defina:
   - Nome da instância: `meu-servidor-web`
   - AMI: `Amazon Linux 2023` (ou Ubuntu)
   - Tipo de instância: `t2.micro` (Free Tier)
4. Crie ou selecione um par de chaves SSH.
5. Configure rede e segurança:
   - Permitir portas: **22 (SSH)**, **80 (HTTP)**, **443 (HTTPS)**
6. (Opcional) No campo "User Data", adicione script de bootstrap, por exemplo:

   ```bash
   #!/bin/bash
   yum update -y
   yum install -y httpd
   systemctl start httpd
   systemctl enable httpd
   echo "Olá, Adriano! Bem-vindo à AWS!" > /var/www/html/index.html
