FROM fluent/fluentd:v1.2.4-onbuild

ENV GEM_PATH /fluentd/vendor/bundle/ruby/2.4.0
COPY Gemfile /Gemfile

RUN apk add --update --virtual .build-deps \
        sudo build-base ruby-dev \
    && sudo gem install bundler \
    && bundle install --path /fluentd/vendor/bundle \
    && sudo gem sources --clear-all \
    && apk del .build-deps \
    && rm -rf /var/cache/apk/* /home/fluent/.gem/ruby/2.4.0/cache/*.gem \
    && mkdir -p /var/log/fluent && chmod 777 /var/log/fluent
