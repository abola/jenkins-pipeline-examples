FROM ubuntu AS dependency

WORKDIR /opt

RUN apt update && apt -y install curl && \
    curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash

FROM bitnami/kubectl:latest

USER root

WORKDIR /tmp

COPY . /tmp

RUN chmod +x /tmp/entrypoint.sh

COPY --from=0 /usr/local/bin/helm /usr/local/bin/helm

ENTRYPOINT ["/tmp/entrypoint.sh"]

CMD ["kubectl"]
