FROM wshihadeh/fluentd-base:1.0.0
MAINTAINER Al-waleed Shihadeh <wshihadeh.dev@gmail.com>

COPY ./config/*.conf /fluentd/etc/

COPY entrypoint.sh /bin/
RUN chmod +x /bin/entrypoint.sh
