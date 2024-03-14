FROM node:18-alpine
WORKDIR /countries-app
COPY package.json .
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]