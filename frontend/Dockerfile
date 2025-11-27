# ------------ Stage 1: Build Angular App ------------
FROM node:18-slim
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
# RUN npm install -g serve
RUN npm run build --prod
EXPOSE 80
CMD ["npx", "serve", "-s", "dist/angular-15-crud/", "-l", "80"]
