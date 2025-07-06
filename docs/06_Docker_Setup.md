# 06_Docker_Setup_App_EBD

## 1. Visão Geral do Docker e Docker Compose

Para garantir um ambiente de desenvolvimento consistente e facilitar a implantação futura, o aplicativo EBD será containerizado usando Docker. O Docker Compose será utilizado para orquestrar os múltiplos serviços (backend, frontend, banco de dados) em um ambiente local.

## 2. Dockerfile do Backend (Spring Boot)

O `Dockerfile` para a aplicação Spring Boot está localizado em `backend/Dockerfile`. Ele define como a imagem Docker do backend será construída.

```dockerfile
# ebd-app/backend/Dockerfile

# Usar uma imagem base oficial do OpenJDK com Alpine Linux para ser leve
FROM openjdk:17-jdk-slim-buster

# Definir o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copiar o arquivo JAR da sua aplicação (assumindo que será gerado em 'target/')
# O nome do JAR pode variar, verifique o seu pom.xml ou build.gradle
# Ex: backend-0.0.1-SNAPSHOT.jar
COPY target/backend-0.0.1-SNAPSHOT.jar app.jar

# Expor a porta que o Spring Boot usa (padrão 8080)
EXPOSE 8080

# Comando para executar a aplicação quando o contêiner iniciar
ENTRYPOINT ["java", "-jar", "app.jar"]
```
