FROM node:10-alpine as builder

ENV API_URL=http://localhost/api/

WORKDIR app/

COPY . .

RUN npm install \
    && npm run build


FROM nginx

COPY --from=builder /app/dist /usr/share/nginx/html
