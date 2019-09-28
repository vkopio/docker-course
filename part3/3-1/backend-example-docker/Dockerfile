FROM ubuntu:18.04

WORKDIR app/

RUN apt-get update \
    && apt-get install -y curl \
    && curl -sL https://deb.nodesource.com/setup_10.x | bash \
    && apt-get update \
    && apt-get install -y nodejs \
    && apt-get purge -y --auto-remove curl \
    && rm -rf /var/lib/apt/lists/* 

ENV FRONT_URL=http://localhost/

COPY . .

RUN npm install

EXPOSE 8000

CMD ["npm", "start"]
