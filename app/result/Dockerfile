# Build site with node image
FROM node:12-alpine
WORKDIR /app
COPY package*.json ./
RUN ls -l
RUN npm install --production
COPY . .
RUN ls -l
RUN npm run build

# Build nginx image
FROM nginx:1.18
EXPOSE 80
WORKDIR /usr/share/nginx/html
COPY --from=node-builder /usr/src/app/dist .
