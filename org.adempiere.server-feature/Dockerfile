FROM openjdk:11-jdk

LABEL maintainer="riad.mennour@owiin.com"

ENV IDEMPIERE_VERSION 8.2
ENV IDEMPIERE_HOME /opt/idempiere
ENV IDEMPIERE_PLUGINS_HOME $IDEMPIERE_HOME/plugins
ENV IDEMPIERE_LOGS_HOME $IDEMPIERE_HOME/log

WORKDIR $IDEMPIERE_HOME

RUN apt-get update && \
    apt-get install -y --no-install-recommends nano postgresql-client && \
    rm -rf /var/lib/apt/lists/*

ADD . $IDEMPIERE_HOME

RUN chmod 777 -R $IDEMPIERE_HOME

RUN ln -s $IDEMPIERE_HOME/idempiere-server.sh /usr/bin/idempiere

RUN chmod +x docker-entrypoint.sh

ENTRYPOINT ["./docker-entrypoint.sh"]
CMD ["idempiere"]
