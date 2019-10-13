FROM ruby:2.6
RUN apt-get update -qq && \
    apt-get install -y apt-utils \
        build-essential \
        libpq-dev \
        default-mysql-client && \
        curl -sL https://deb.nodesource.com/setup_12.x | bash - && \
        apt-get install -y nodejs && \
        npm install yarn --global
RUN mkdir /app
WORKDIR /app
ADD Gemfile /app/Gemfile
ADD Gemfile.lock /app/Gemfile.lock
RUN bundle install -j4
ADD . /app

EXPOSE 8888