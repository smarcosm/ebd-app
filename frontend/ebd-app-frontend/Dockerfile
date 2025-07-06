
# --- STAGE 1: Build da Aplicação Angular ---
FROM node:22-alpine3.22 as build

# Update apk packages to ensure latest security patches
RUN apk update && apk upgrade

WORKDIR /app

# Copiar package.json e package-lock.json para instalar dependências
COPY package.json package-lock.json ./
RUN npm install

# Copiar todo o código fonte da aplicação
COPY . .

# Construir a aplicação Angular para produção
# O --output-path deve corresponder ao caminho onde o Angular CLI gera os arquivos
RUN npm run build -- --output-path=./dist/ebd-app-frontend/browser --configuration=production

# --- STAGE 2: Servir com Nginx ---
FROM nginx:alpine

# Copiar a configuração do Nginx (vamos criar este arquivo em breve)
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copiar os arquivos estáticos da aplicação Angular do estágio de build
COPY --from=build /app/dist/ebd-app-frontend/browser /usr/share/nginx/html

# Expor a porta padrão do Nginx
EXPOSE 80

# Comando padrão do Nginx
CMD ["nginx", "-g", "daemon off;"]
