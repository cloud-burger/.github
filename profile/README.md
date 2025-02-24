# 🍔 Cloud Burger - Self Service

## 📊 Visão Geral
O projeto **Cloud Burger** é uma solução de *Self Service* desenvolvida para otimizar a experiência do cliente em restaurantes e lanchonetes. Este ecossistema é composto por uma aplicação central e uma infraestrutura de suporte altamente escalável, utilizando Kubernetes, banco de dados gerenciado, e autenticação robusta. A imagem abaixo ilustra a iteração entre a infraestrutura e a aplicação.

![infra_cloud_burger-Arquitetura Fase 4 drawio (1)](https://github.com/user-attachments/assets/84f04a7d-e3d3-4939-bd18-212ce15747a4)


🔀 Fluxo de Requisições

- **Autorização**

![infra_cloud_burger-Fluxo de autorização drawio](https://github.com/user-attachments/assets/b6bb5d71-a690-427a-bb74-fe8587952b79)

- **Pedido**

![infra_cloud_burger-Fluxo de pedido drawio](https://github.com/user-attachments/assets/8d5cae6e-f593-4472-9d8d-b41543f04c2a)

---
🛢️ Serviços

**Orders App**
- Gerencia o CRUD de pedidos no Orders Database (PostgreSQL)
- Consome mensagens da fila de pagamentos (Payments Status Queue - SQS) para validar pagamentos.

**Payments App**
- Produz mensagens na fila de pagamento (SQS).
- Gerencia transações financeiras no Payments Database (PostgreSQL).

**Customers App**
- Executa operações CRUD de clientes no Customers Database (DynamoDB).
- Consulta CPF na base de clientes para validação via AWS Lambda.


🔁 **Integração Assíncrona**
- O Payments App interage com a Payments Status Queue (SQS) na fila: process-order-payment-queue para processar pagamentos de forma assíncrona.

### 📄 Repositórios Principais:

1. **Infraestrutura**:
   - [🔑 Self Service Auth Infra](https://github.com/cloud-burger/self-service-auth-infra)
   - [⚛️ Self Service Kubernetes](https://github.com/cloud-burger/self-service-k8s)
   - [📁 Self Service Database](https://github.com/cloud-burger/self-service-database)
   - [🔒 Self Service Auth](https://github.com/cloud-burger/self-service-auth)

2. **📚 Aplicação**:
   - [🙋🏼 Customers](https://github.com/cloud-burger/customers)
   - [🧾 Orders](https://github.com/cloud-burger/orders)
   - [💸 Payments](https://github.com/cloud-burger/payments)
   - [🍔 Self Service](https://github.com/cloud-burger/self-service)(Deprecated)

---

## 📋 Detalhes

### 1. [🔑 Self Service Auth Infra](https://github.com/cloud-burger/self-service-auth-infra)
Este repositório contém a infraestrutura necessária para a autenticação, garantindo segurança e escalabilidade. Cria uma infraestrutura na AWS utilizando Terraform como ferramenta de Infraestructure as Code (IaC) para provisionar um Lambda Authorizer e um API Gateway.

**Principais Componentes:**
- 🔧 Provisionamento da infa necessária.
- 🛡️ Configuração do cognito.

### 2. [⚛️ Self Service Kubernetes](https://github.com/cloud-burger/self-service-k8s)
Infraestrutura baseada em Kubernetes para orquestração e deploy de todos os serviços. Este repositório fornece *manifests* e *Helm charts* para provisionamento de workloads.

**Principais Componentes:**
- 🌐 Deployment automatizado.
- 🛣️ Balanceamento de carga.
- 🌆 Escalabilidade automática.

### 3. [📁 Self Service Database](https://github.com/cloud-burger/self-service-database)
Provisionamento e Configurações para o banco de dados da aplicação.

**Principais Componentes:**
- 🔧 Provisionamento de um RDS PostgreSQL público

### 4. [🔒 Self Service Auth](https://github.com/cloud-burger/self-service-auth)
Responsável pelo sistema de autenticação e autorização da aplicação, implementando fluxos seguros e fáceis de integrar.

**Principais Componentes:**
- 🔑 Implementação de autenticação via tokens JWT.
- 📢 Fluxos de login social.

### 5. [🙋🏼 Customers](https://github.com/cloud-burger/customers)
Este repositório centraliza a aplicação para a experiência de cadastro e busca dos clientes.

### 6. [🧾 Orders](https://github.com/cloud-burger/orders)
Este repositório centraliza a aplicação responsável pelo gerenciamento de pedidos. Conta com testes BDD

### 7. [💸 Payments](https://github.com/cloud-burger/payments)
Este repositório centraliza a aplicação responsável pelo gerenciamento de pagamentos, desde a criação até a baixa como pago.

### 8. [🍔 Self Service](https://github.com/cloud-burger/self-service)
A aplicação do projeto Self Service. Este repositório centraliza a experiência do usuário, pedido e compra. Foi depreciado após a quebra da aplicação em multi-repo.

**Componentes Comuns entre as aplicações:**
- 📲  API nos padrões RESTFull.
- 📲  Documentação OpenApi com Swagger.
- 📡 Integrações com APIs de autenticação e banco de dados.
- 🧪 Cobertura de testes com Sonar Qube.

---

## 🛠️ Configuração e Uso
Para configurar o ecossistema completo, siga os passos abaixo:

### 1. 📓 Clone os Repositórios
```bash
# Clonar todos os repositórios
git clone https://github.com/cloud-burger/self-service-auth-infra
git clone https://github.com/cloud-burger/self-service-k8s
git clone https://github.com/cloud-burger/self-service-database
git clone https://github.com/cloud-burger/self-service-auth
git clone https://github.com/cloud-burger/customers
git clone https://github.com/cloud-burger/orders
git clone https://github.com/cloud-burger/payments
```

### 2. 💡 Configure o Ambiente
- Certifique-se de ter instalado:
  - 🛠️ Docker e Kubernetes.
  - 🌱 Helm para gestão de *charts*.
  - 🗒️ Ferramentas de migração de banco de dados (como Flyway ou Liquibase).

- Configure as variáveis de ambiente conforme os arquivos `.env` de cada repositório.

### 3. 🔄 Inicialize os Serviços
Siga os passos descritos em cada repositório para inicializar os serviços.

Exemplo para aplicação principal:
```bash
cd self-service
npm install
npm start
```

---

## 📚 Contribuição
Contribuições são bem-vindas! Siga as diretrizes abaixo:

1. 🌐 **Fork o Repositório**.
2. 🔧 Crie uma *branch* para sua feature ou correção.
3. 📥 Envie um *Pull Request* com a descrição detalhada das alterações.

---

## 📃 Licença
Este projeto está licenciado sob a [Licença MIT](https://opensource.org/licenses/MIT).
