FROM node:18-alpine as base
WORKDIR /frontend
EXPOSE 3000

FROM base as dev
COPY package.json .
RUN npm install
COPY . .
CMD ["npm", "start"]

FROM base as prod
COPY package.json .
RUN npm install --production
COPY . .
CMD ["node", "src/index.tsx"]