FROM ubuntu:18.04

WORKDIR app/

RUN apt-get update \
    && apt-get install -y curl \
    && curl -sL https://deb.nodesource.com/setup_10.x | bash \
    && apt-get update \
    && apt-get install -y nodejs \
    && npm install -g serve \
    && apt-get purge -y --auto-remove curl \
    && rm -rf /var/lib/apt/lists/* 

ENV API_URL=http://localhost/api/

COPY . .

RUN npm install \
    && npm run build

EXPOSE 5000

CMD ["serve", "-s", "-l", "5000", "dist"]
