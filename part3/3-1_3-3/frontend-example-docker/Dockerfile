FROM ubuntu:18.04

ENV API_URL=http://localhost/api/

RUN apt-get update \
    && apt-get install -y curl \
    && curl -sL https://deb.nodesource.com/setup_10.x | bash \
    && apt-get update \
    && apt-get install -y nodejs \
    && npm install -g serve \
    && apt-get purge -y --auto-remove curl \
    && rm -rf /var/lib/apt/lists/* \
    && useradd -m app

WORKDIR app/

COPY . .

RUN chown -R app:app .

USER app

RUN npm install \
    && npm run build

EXPOSE 5000

CMD ["serve", "-s", "-l", "5000", "dist"]
