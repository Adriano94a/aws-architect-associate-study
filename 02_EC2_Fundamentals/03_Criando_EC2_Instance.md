# 🚀 Minha Primeira Instância EC2 Criada pelo Usuário Tais

Este tutorial detalha a criação e configuração inicial de uma instância EC2 na AWS, destacando pontos importantes para quem está começando e quer entender o processo com exemplos práticos.

---

## 🏷️ Definindo Nome e Tags

Ao criar a instância, definimos um **nome amigável** e adicionamos **tags** para organizar e identificar recursos na nuvem.

### Por que usar tags?

- Facilita a **identificação** e o **gerenciamento** em ambientes com várias instâncias.
- Ajuda no controle de custos, agrupando recursos por projeto, time ou finalidade.
- Fundamental para **automação** e criação de políticas na AWS.

---

## 🐧 Escolha do Sistema Operacional

Usamos a **Amazon Linux AWS** como sistema operacional, que é otimizada para execução na AWS e tem suporte oficial, além de estar no Free Tier.

---

## 🖥️ Verificando o Tipo da Instância

Após criar, é possível conferir o tipo da instância, que indica a configuração de recursos disponíveis:

- Exemplo usado: **t2.micro**, que está incluso no Free Tier da AWS.
- Esse tipo de instância oferece **1 vCPU** e **1 GB de RAM**, ideal para testes e aplicações leves.

---

## 🔑 Key Pair e SSH

### O que é o Key Pair?

- É o par de chaves criptográficas usado para acesso seguro via SSH à instância.
- No exemplo, usamos um key pair chamado **ec2-tutorial**.

### Tipo de chave

- **RSA** é o algoritmo criptográfico padrão para criação do par de chaves.
- O arquivo privado é gerado no formato **`.pem`** (Privacy Enhanced Mail), usado em sistemas Linux/macOS.
- O formato **`.ppk`** (PuTTY Private Key) é utilizado no Windows com o cliente PuTTY.
- Para usar `.pem` no Windows com PuTTY, é necessário converter `.pem` para `.ppk` usando a ferramenta **PuTTYgen**.

---

## 🔥 Configuração do Security Group (Firewall)

### Permissões configuradas

- **Allow SSH traffic from**: Libera a porta 22 para acesso remoto seguro via SSH.
- **Allow HTTP traffic**: Libera a porta 80, permitindo que o servidor web receba requisições HTTP externas.

### Importância

- Sem liberar essas portas, não conseguiríamos acessar a instância nem servir páginas web.
- Segurança: limitar o acesso a IPs ou faixas específicas aumenta a proteção.

---

## 💽 Volume Raiz (Root Volume)

- Foi criado um volume raiz de **8 GiB**, padrão para a maioria das AMIs.
- Esse volume armazena o sistema operacional e dados persistentes da instância.

---

## ⚙️ User Data — Script de Inicialização (Bootstrap)

Na aba **Advanced > User Data**, podemos inserir comandos que serão executados automaticamente na primeira inicialização da instância.

### Exemplo de script para instalação de servidor web Apache:

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Meu primeiro servidor web na AWS - criado pelo usuário Tais</h1>" > /var/www/html/index.html


# Características da Instância EC2 Após Criação

Ao visualizar sua instância no console AWS, alguns campos essenciais ajudam a entender o status, configurações e acessos disponíveis:

| Campo                | Descrição                                                                                          |
|----------------------|--------------------------------------------------------------------------------------------------|
| **Instance ID**      | Identificador único da instância, usado para gerenciamento e auditoria.                           |
| **Instance State**   | Estado atual da instância (ex: `running`, `stopped`, `terminated`).                              |
| **Instance Type**    | Tipo da instância, que define CPU, RAM e outras características (ex: `t2.micro`).                |
| **Public IPv4 Address** | Endereço IP público acessível pela internet para conexões externas (SSH, HTTP, etc.).          |
| **Private IPv4 Address**| IP interno da VPC para comunicação entre recursos na rede AWS (não acessível externamente).     |
| **Security Groups**  | Grupos de segurança (firewall) que definem regras de entrada e saída para a instância.            |
| **Key Pair Name**    | Nome do par de chaves usado para autenticação SSH.                                               |
| **Launch Time**      | Data e hora em que a instância foi criada.                                                      |

---

# Resumo - Criando e Configurando sua Instância EC2

1. **Nome e Tags:** Essenciais para organização, controle de custos e automação.

2. **Sistema Operacional:** Escolha adequada para o uso desejado; Amazon Linux é otimizada para AWS.

3. **Tipo de Instância:** Define capacidade computacional e memória; escolha Free Tier (`t2.micro`) para testes.

4. **Key Pair (RSA `.pem`):** Usado para acesso SSH seguro; `.pem` para Linux/macOS, `.ppk` para PuTTY no Windows.

5. **Security Groups:** Configuram firewall; liberar portas SSH (22) e HTTP (80) é fundamental para acesso remoto e web.

6. **Volume Raiz:** Armazena o sistema e dados; geralmente 8 GiB padrão.

7. **User Data (Bootstrap):** Automatiza configurações iniciais via script, como instalar e iniciar um servidor web.

8. **IPs Públicos vs Privados:**  
   - Público: permite acesso da internet.  
   - Privado: comunicação interna na AWS.

---

Esse conteúdo pode ser usado como base para documentação, treinamentos ou checklist para iniciantes na AWS.
