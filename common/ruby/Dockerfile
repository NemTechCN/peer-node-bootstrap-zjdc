FROM techbureau/catapult-tools:gcc-0.9.5.1
RUN apt update
RUN apt install -y ruby
# for debug
RUN apt install -y ruby-dev make g++

WORKDIR /usr/app

COPY symbol-utilities.gemspec /usr/app/
COPY Gemfile /usr/app/ 
COPY Gemfile.lock /usr/app/ 
ADD lib /usr/app/lib
ADD bin /usr/app/bin
ADD spec /usr/app/spec

RUN gem install bundler -v "$(grep -A 1 "BUNDLED WITH" Gemfile.lock | tail -n 1)"
#ARG BUNDLE_GITHUB__COM 
RUN bundle install

