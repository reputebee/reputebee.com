FROM jekyll/jekyll:4.2.2
RUN apk add curl && apk add --update nodejs npm 

RUN npm install -g npm@latest
WORKDIR /srv/jekyll
COPY ./package.json /srv/jekyll
RUN npm install && npm cache clean --force
RUN gem update --system
RUN gem install bundler:2.3.25
COPY Gemfile .
RUN bundle install
COPY . .
EXPOSE 4000
CMD ["jekyll", "serve", "--watch", "--force_polling"]
