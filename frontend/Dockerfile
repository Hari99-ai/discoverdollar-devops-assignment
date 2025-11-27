FROM node:18-alpine as builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build -- --prod

FROM nginx:stable-alpine
COPY --from=builder /app/dist/your-angular-app-name /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
