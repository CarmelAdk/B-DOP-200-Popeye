# Build site with node image
FROM node:12-alpine
WORKDIR /app
EXPOSE 3000
COPY package*.json ./
RUN npm install --production
COPY . .
ENTRYPOINT ["npm", "start"]
