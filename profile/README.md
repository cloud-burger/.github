# 🍔 Cloud Burger - Self Service

## 📊 Visão Geral
O projeto **Cloud Burger** é uma solução de *Self Service* desenvolvida para otimizar a experiência do cliente em restaurantes e lanchonetes. Este ecossistema é composto por uma aplicação central e uma infraestrutura de suporte altamente escalável, utilizando Kubernetes, banco de dados gerenciado, e autenticação robusta.

![infra_diagram drawio](https://github.com/user-attachments/assets/65ba327a-e43b-4d10-838f-bbece4c7eddf)

A imagem acima ilustra a iteração entre a infraestrutura e a aplicação. Destaca-se principalmente a autorização dos recursos, que possui duas formas:
- Rotas privadas, como a de cadastro dos produtos, são autorizadas usando tokens gerados pelo cognito, onde os adminitradores da aplicação estarão cadastrados.
- Rotas públicas, como a de pedidos, será autorizada com uso de um lambda authorizer, que consulta nossa base de clientes no RDS.


### 📄 Repositórios Principais:

1. **Infraestrutura**:
   - [🔑 Self Service Auth Infra](https://github.com/cloud-burger/self-service-auth-infra)
   - [⚛️ Self Service Kubernetes](https://github.com/cloud-burger/self-service-k8s)
   - [📁 Self Service Database](https://github.com/cloud-burger/self-service-database)
   - [🔒 Self Service Auth](https://github.com/cloud-burger/self-service-auth)

2. **📚 Aplicação**:
   - [🍔 Self Service](https://github.com/cloud-burger/self-service)

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

### 5. [🍔 Self Service](https://github.com/cloud-burger/self-service)
A aplicação principal do projeto Self Service. Este repositório centraliza a experiência do usuário, com endpoints no padrão RESTFull e integrações aos módulos de infraestrutura.

**Principais Componentes:**
- 📲  API nos padrões RESTFull.
- 📲  Documentação OpenApi com Swagger.
- 📡 Integrações com APIs de autenticação e banco de dados.
- 💼 Lógica de negócios e gestão de pedidos.

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
git clone https://github.com/cloud-burger/self-service
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
