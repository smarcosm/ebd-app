
# Usar uma imagem base oficial do OpenJDK com Alpine Linux para ser leve
FROM openjdk:17-jdk-slim-buster

# Definir o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copiar o arquivo JAR da sua aplicação (assumindo que será gerado em 'target/')
# O nome do JAR pode variar, verifique o seu pom.xml ou build.gradle
# Ex: backend-0.0.1-SNAPSHOT.jar
COPY build/libs/demo-0.0.1-SNAPSHOT.jar app.jar

# Expor a porta que o Spring Boot usa (padrão 8080)
EXPOSE 8080

# Comando para executar a aplicação quando o contêiner iniciar
ENTRYPOINT ["java", "-jar", "app.jar"]