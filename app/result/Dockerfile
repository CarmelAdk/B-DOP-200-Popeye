# Build site with node image
FROM node:12-alpine
WORKDIR /app
EXPOSE 3000
COPY package*.json ./
RUN ls -l
RUN npm install --production
COPY . .
RUN ls -l
CMD ["npm", "start"]
