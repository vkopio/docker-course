FROM ubuntu:18.04

RUN apt-get update \
    && apt-get install -y curl \
    && curl -sL https://deb.nodesource.com/setup_10.x | bash \
    && apt-get update \
    && apt-get install -y nodejs

WORKDIR app/

COPY . .

ENV FRONT_URL=http://localhost/

RUN npm install

EXPOSE 8000

CMD ["npm", "start"]
