# 🍔 Cloud Burger - Self Service Ecosystem

## 📊 Visão Geral
O projeto **Cloud Burger** é uma solução completa de *Self Service* desenvolvida para otimizar a experiência do cliente em restaurantes e lanchonetes. Este ecossistema é composto por uma aplicação central e uma infraestrutura de suporte altamente escalável, utilizando Kubernetes, banco de dados gerenciado, e autenticação robusta.

### 📄 Repositórios Principais:

1. **Infraestrutura**:
   - [🔑 Self Service Auth Infra](https://github.com/cloud-burger/self-service-auth-infra)
   - [⚛️ Self Service Kubernetes](https://github.com/cloud-burger/self-service-k8s)
   - [📁 Self Service Database](https://github.com/cloud-burger/self-service-database)
   - [🔒 Self Service Auth](https://github.com/cloud-burger/self-service-auth)

2. **📚 Aplicação**:
   - [🍔 Self Service](https://github.com/cloud-burger/self-service)

---

## 📋 Repositórios em Detalhes

### 1. [🔑 Self Service Auth Infra](https://github.com/cloud-burger/self-service-auth-infra)
Este repositório contém a infraestrutura necessária para a autenticação, garantindo segurança e escalabilidade. Utiliza integrações como OAuth2, OpenID Connect e provisionamento automático de serviços relacionados.

**Principais Componentes:**
- 🔧 Configurações de provedores de identidade.
- 🛡️ Suporte para multi-tenant.

### 2. [⚛️ Self Service Kubernetes](https://github.com/cloud-burger/self-service-k8s)
Infraestrutura baseada em Kubernetes para orquestração e deploy de todos os serviços. Este repositório fornece *manifests* e *Helm charts* para provisionamento de workloads.

**Principais Componentes:**
- 🌐 Deployment automatizado.
- 🛣️ Balanceamento de carga.
- 🌆 Escalabilidade automática.

### 3. [📁 Self Service Database](https://github.com/cloud-burger/self-service-database)
Configurações e scripts para o banco de dados da aplicação. Inclui suporte para migrações e backups automatizados.

**Principais Componentes:**
- 🔧 Scripts de inicialização.
- 🔐 Rotinas de backup.
- 📊 Migrações com ferramentas como Flyway.

### 4. [🔒 Self Service Auth](https://github.com/cloud-burger/self-service-auth)
Responsável pelo sistema de autenticação e autorização da aplicação, implementando fluxos seguros e fáceis de integrar.

**Principais Componentes:**
- 🔑 Implementação de autenticação via tokens JWT.
- 📢 Fluxos de login social.

### 5. [🍔 Self Service](https://github.com/cloud-burger/self-service)
A aplicação principal do ecossistema Self Service. Este repositório centraliza a experiência do usuário, com interfaces responsivas e integrações aos módulos de infraestrutura.

**Principais Componentes:**
- 📲 UI responsiva.
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
