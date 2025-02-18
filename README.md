# FiapEats - Infraestrutura do Banco de Dados do Microserviço de Produtos

Este repositório contém a configuração do Terraform para gerenciar a infraestrutura do banco de dados do Microserviço de Produtos do **FiapEats**.

O **Terraform** é utilizado para provisionar e gerenciar a infraestrutura necessária para o banco de dados do microserviço de produtos, garantindo que ela seja versionada, replicável e fácil de manter.

## Estrutura do Repositório

- **terraform.yaml**: Arquivo de configuração do GitHub Actions para automatizar a execução do Terraform (`plan`, `apply` e `destroy`) ao fazer push para a branch `main`.
- **variables.tf**: Arquivo de variáveis do Terraform, onde é definida a variável `destroy_infra`, que controla se a infraestrutura deve ser destruída ou aplicada.
- **terraform.tfvars**: Arquivo de variáveis personalizadas (*não incluído no repositório por questões de segurança*), mas pode ser criado localmente para definir valores como `destroy_infra = false`.

## Como Rodar o Terraform

### **Pré-requisitos**

1. **Terraform instalado**: Certifique-se de que o Terraform está instalado na sua máquina. Verifique a instalação com o comando:
   ```bash
   terraform --version
   ```
2. **Credenciais da AWS**: Configure as credenciais da AWS no seu ambiente:
   ```bash
   export AWS_ACCESS_KEY_ID="sua_access_key"
   export AWS_SECRET_ACCESS_KEY="sua_secret_key"
   ```

### **Passos para Executar o Terraform**

1. **Inicializar o Terraform**:
   ```bash
   terraform init
   ```
2. **Validar a Configuração**:
   ```bash
   terraform validate
   ```

3. **Aplicar a Infraestrutura**:
   ```bash
   terraform apply -auto-approve
   ```
4. **Destruir a Infraestrutura (opcional)**:
   ```bash
   terraform destroy 
   ```
