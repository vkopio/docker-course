FROM ruby:2.6.0

RUN apt-get update && apt-get install -y nodejs sqlite3

WORKDIR app/

COPY . .

RUN gem install bundler
RUN bundle install
RUN rails db:migrate

EXPOSE 3000

CMD ["rails", "s"]
