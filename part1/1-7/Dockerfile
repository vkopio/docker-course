FROM ubuntu

RUN apt-get update && apt-get install -y curl

WORKDIR /app

COPY search.sh .

CMD ["./search.sh"]
