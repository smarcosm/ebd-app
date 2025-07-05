# 04_Backend_Setup_App_EBD

## 1. Configuração do Projeto Spring Boot

Esta seção detalha a criação e configuração inicial do projeto backend, utilizando Spring Boot.

### 1.1. Geração do Projeto

O projeto foi gerado através do [Spring Initializr](https://start.spring.io/) com as seguintes especificações:

* **Ferramenta de Build:** Maven (ou Gradle, se escolhido)
* **Linguagem:** Java
* **Versão do Spring Boot:** 3.5.3 (ou a versão estável mais recente na data de criação)
* **Metadata:**
  * **Group:** `com.ebdapp`
  * **Artifact:** `backend`
  * **Name:** `EBDAppBackend`
  * **Description:** `Backend para o aplicativo de gerenciamento da EBD`
  * **Package Name:** `com.ebdapp.backend`
  * **Packaging:** Jar
  * **Java:** 17 (ou a versão utilizada)

### 1.2. Dependências Iniciais

As seguintes dependências foram selecionadas no Spring Initializr e adicionadas ao arquivo `build.gradle` (para Gradle):

* `Spring Web`: Para construir aplicações web, incluindo APIs RESTful.
* `Spring Data JPA`: Para simplificar o acesso a dados usando a API de Persistência Java (JPA) e Hibernate como implementação padrão.
* `PostgreSQL Driver`: Conector JDBC para interagir com o banco de dados PostgreSQL.
* `Spring Security`: Para implementar recursos de autenticação e autorização robustos.
* `Lombok` (opcional): Biblioteca para reduzir o código boilerplate (getters, setters, construtores, etc.).
* `Validation`: Para validação de dados de entrada usando JSR-303 (Hibernate Validator).
* `Spring Boot DevTools` (opcional): Ferramentas que melhoram a experiência de desenvolvimento (ex: recarga automática).

### 1.3. Estrutura de Pastas Inicial

A estrutura básica de pastas gerada para o backend é:
backend/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/ebdapp/backend/   # Pacote raiz da aplicação
│   │   │       └── EbdAppBackendApplication.java # Classe principal da aplicação
│   │   └── resources/              # Arquivos de configuração, estáticos, templates
│   │       └── application.properties # ou application.yml
│   └── test/
│       └── java/                   # Testes unitários e de integração
└── build.gradle       # Arquivo de configuração do projeto Gradle

---

## 2. Configuração Inicial do Banco de Dados (PostgreSQL)

A configuração inicial de conexão com o banco de dados PostgreSQL será feita no arquivo `src/main/resources/application.properties` (ou `application.yml`).

**Para Ambiente de Desenvolvimento Local (com Docker Compose, que será configurado em `06_Docker_Setup.md`):**

```properties
# application.properties
spring.datasource.url=jdbc:postgresql://localhost:5432/ebd_db
spring.datasource.username=ebd_user
spring.datasource.password=ebd_password
spring.datasource.driver-class-name=org.postgresql.Driver

# Configurações JPA/Hibernate
spring.jpa.hibernate.ddl-auto=update # Pode ser 'create-drop' para testes, 'update' para desenvolvimento
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

# Configurações do servidor web (Tomcat embutido)
server.port=8080

```
