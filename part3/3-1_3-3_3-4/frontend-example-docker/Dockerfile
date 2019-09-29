FROM node:10-alpine

ENV API_URL=http://localhost/api/

RUN npm install -g serve \
    && adduser -D app

WORKDIR app/

COPY . .

RUN chown -R app:app .

USER app

RUN npm install \
    && npm run build

EXPOSE 5000

CMD ["serve", "-s", "-l", "5000", "dist"]
