FROM docker.io/bitnami/minideb:bullseye

ARG TARGETARCH

LABEL org.opencontainers.image.authors="https://bitnami.com/contact" \
      org.opencontainers.image.description="Application packaged by Bitnami" \
      org.opencontainers.image.ref.name="2.6.1-debian-11-r23" \
      org.opencontainers.image.source="https://github.com/bitnami/containers/tree/main/bitnami/grafana-loki" \
      org.opencontainers.image.title="grafana-loki" \
      org.opencontainers.image.vendor="VMware, Inc." \
      org.opencontainers.image.version="2.6.1"

ENV HOME="/" \
    OS_ARCH="${TARGETARCH:-amd64}" \
    OS_FLAVOUR="debian-11" \
    OS_NAME="linux"

COPY prebuildfs /
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
# Install required system packages and dependencies
RUN install_packages ca-certificates curl gzip procps tar
RUN mkdir -p /tmp/bitnami/pkg/cache/ && cd /tmp/bitnami/pkg/cache/ && \
    if [ ! -f grafana-loki-2.6.1-2-linux-${OS_ARCH}-debian-11.tar.gz ]; then \
      curl -SsLf https://downloads.bitnami.com/files/stacksmith/grafana-loki-2.6.1-2-linux-${OS_ARCH}-debian-11.tar.gz -O ; \
      curl -SsLf https://downloads.bitnami.com/files/stacksmith/grafana-loki-2.6.1-2-linux-${OS_ARCH}-debian-11.tar.gz.sha256 -O ; \
    fi && \
    sha256sum -c grafana-loki-2.6.1-2-linux-${OS_ARCH}-debian-11.tar.gz.sha256 && \
    tar -zxf grafana-loki-2.6.1-2-linux-${OS_ARCH}-debian-11.tar.gz -C /opt/bitnami --strip-components=2 --no-same-owner --wildcards '*/files' && \
    rm -rf grafana-loki-2.6.1-2-linux-${OS_ARCH}-debian-11.tar.gz grafana-loki-2.6.1-2-linux-${OS_ARCH}-debian-11.tar.gz.sha256
RUN apt-get update && apt-get upgrade -y && \
    apt-get clean && rm -rf /var/lib/apt/lists /var/cache/apt/archives
RUN chmod g+rwX /opt/bitnami
RUN mkdir -p /bitnami/grafana-loki/data /bitnami/grafana-loki/loki /bitnami/grafana-loki/wal && chmod -R g+rwX /bitnami/grafana-loki && ln -s  /bitnami/grafana-loki/loki /loki && ln -s /bitnami/grafana-loki/data /data && ln -s /bitnami/grafana-loki/wal /wal

ENV APP_VERSION="2.6.1" \
    BITNAMI_APP_NAME="grafana-loki" \
    PATH="/opt/bitnami/grafana-loki/bin:$PATH"

EXPOSE 3100

USER 1001
ENTRYPOINT [ "loki" ]
CMD [ "-config.file=/bitnami/grafana-loki/conf/loki.yaml" ]
