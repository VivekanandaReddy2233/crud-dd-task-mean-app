FROM node:16 AS build

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build --prod

FROM nginx:alpine

# Copy ONLY the CONTENTS of the build folder to Nginx root
COPY --from=build /app/dist/angular-15-crud/ /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

