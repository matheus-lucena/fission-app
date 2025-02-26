FROM --platform=linux/arm64 node:22-alpine

# Define o diretório de trabalho
WORKDIR /app

# Copia os arquivos da função e instala dependências
COPY package*.json ./
RUN npm install --only=production
COPY . .

# Porta utilizada pelo Fission para chamadas HTTP
ENV PORT=8080
EXPOSE 8080

# Comando para iniciar a função no Fission
CMD ["node", "handler.js"]
