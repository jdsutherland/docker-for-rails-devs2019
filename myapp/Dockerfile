FROM ruby:2.7.1

# Ensure latest packages for Yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | APT_KEY_DONT_WARN_ON_DANGEROUS_USAGE=true apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
    apt-get update -yqq && apt-get install -yqq --no-install-recommends \
      nodejs \
      yarn

RUN apt-get update -yqq
RUN apt-get install -yqq --no-install-recommends nodejs yarn

WORKDIR /usr/src/app

COPY . .

RUN bundle install
RUN yarn install
