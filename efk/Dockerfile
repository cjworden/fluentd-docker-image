FROM fluent/fluentd:onbuild
MAINTAINER cjworden

USER root

RUN apk add --update --virtual .build-deps \
        sudo build-base ruby-dev \

 # cutomize following instruction as you wish
 && sudo -u fluent gem install \
        fluent-plugin-secure-forward \
        fluent-plugin-elasticsearch \

 && sudo -u fluent gem sources --clear-all \
 && apk del .build-deps \
 && rm -rf /var/cache/apk/* \
           /home/fluent/.gem/ruby/2.3.0/cache/*.gem

USER fluent

EXPOSE 24284
