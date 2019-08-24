FROM ubuntu:18.04

RUN apt-get update && apt-get install -y curl

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash

RUN apt-get update && apt-get install -y nodejs

WORKDIR app/

RUN npm install -g serve

COPY . .

RUN npm install
RUN npm run build

EXPOSE 8080

CMD ["serve", "-s", "-l", "5000", "dist"]
