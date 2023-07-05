FROM fluent/fluentd:v1.16-1

# Use root account to use apk
USER root

# below RUN includes plugin as examples elasticsearch is not required
# you may customize including plugins as you wish
RUN apk add --no-cache --update --virtual .build-deps \
  sudo build-base ruby-dev \
  && sudo gem install fluent-plugin-record-reformer -v 0.9.1 \
  && sudo gem install fluent-plugin-systemd -v 1.0 \
  && sudo gem install fluent-plugin-kubernetes_metadata_filter -v 2 \
  && sudo gem install fluent-plugin-rewrite-tag-filter -v 2.4 \
  && sudo gem install fluent-plugin-copy_ex -v 0.1.0 \
  && sudo gem install fluent-plugin-route -v 1.0.0 \
  && sudo gem install fluent-plugin-s3 -v 1.6 \
  && sudo gem install fluent-plugin-splunk-hec -v 1.3 \
  && sudo gem install fluent-plugin-prometheus -v 2.0 \
  && sudo gem install fluent-plugin-detect-exceptions -v 0.0.11 \
  && sudo gem sources --clear-all \
  && apk del .build-deps \
  && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

COPY fluent.conf /fluentd/etc/
COPY entrypoint.sh /bin/

USER fluent
