FROM ubuntu:18.04

RUN apt-get update \
    && apt-get install -y curl \
    && curl -sL https://deb.nodesource.com/setup_10.x | bash \
    && apt-get update \
    && apt-get install -y nodejs

WORKDIR app/

RUN npm install -g serve

COPY . .

ENV API_URL=http://localhost:8000

RUN npm install
RUN npm run build

EXPOSE 5000

CMD ["serve", "-s", "-l", "5000", "dist"]
