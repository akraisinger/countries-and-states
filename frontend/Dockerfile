FROM node:18-alpine as base
WORKDIR /frontend
COPY package.json .

FROM base as dev
RUN npm install
EXPOSE 3000
CMD ["npm", "start"]

FROM base as builder
RUN npm install --production
COPY . .
RUN npm run build

FROM nginx:alpine as prod
COPY --from=builder /frontend/build /usr/share/nginx/html