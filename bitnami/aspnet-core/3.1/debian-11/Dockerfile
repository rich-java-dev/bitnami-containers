FROM docker.io/bitnami/minideb:bullseye

ARG TARGETARCH

LABEL org.opencontainers.image.authors="https://bitnami.com/contact" \
      org.opencontainers.image.description="Application packaged by Bitnami" \
      org.opencontainers.image.ref.name="3.1.29-debian-11-r2" \
      org.opencontainers.image.source="https://github.com/bitnami/containers/tree/main/bitnami/aspnet-core" \
      org.opencontainers.image.title="aspnet-core" \
      org.opencontainers.image.vendor="VMware, Inc." \
      org.opencontainers.image.version="3.1.29"

ENV HOME="/app" \
    OS_ARCH="${TARGETARCH:-amd64}" \
    OS_FLAVOUR="debian-11" \
    OS_NAME="linux"

COPY prebuildfs /
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
# Install required system packages and dependencies
RUN install_packages build-essential ca-certificates curl git gzip libbrotli1 libc6 libcap2-bin libcom-err2 libcurl4 libffi7 libgcc-s1 libgcrypt20 libgmp10 libgnutls30 libgpg-error0 libgssapi-krb5-2 libhogweed6 libicu-dev libidn2-0 libk5crypto3 libkeyutils1 libkrb5-3 libkrb5support0 libldap-2.4-2 liblttng-ust-dev libnettle8 libnghttp2-14 libp11-kit0 libpsl5 librtmp1 libsasl2-2 libsqlite3-dev libssh2-1 libssl-dev libssl1.1 libstdc++6 libtasn1-6 libunistring2 pkg-config procps tar unzip wget zlib1g
RUN mkdir -p /tmp/bitnami/pkg/cache/ && cd /tmp/bitnami/pkg/cache/ && \
    if [ ! -f aspnet-core-3.1.29-0-linux-${OS_ARCH}-debian-11.tar.gz ]; then \
      curl -SsLf https://downloads.bitnami.com/files/stacksmith/aspnet-core-3.1.29-0-linux-${OS_ARCH}-debian-11.tar.gz -O ; \
      curl -SsLf https://downloads.bitnami.com/files/stacksmith/aspnet-core-3.1.29-0-linux-${OS_ARCH}-debian-11.tar.gz.sha256 -O ; \
    fi && \
    sha256sum -c aspnet-core-3.1.29-0-linux-${OS_ARCH}-debian-11.tar.gz.sha256 && \
    tar -zxf aspnet-core-3.1.29-0-linux-${OS_ARCH}-debian-11.tar.gz -C /opt/bitnami --strip-components=2 --no-same-owner --wildcards '*/files' && \
    rm -rf aspnet-core-3.1.29-0-linux-${OS_ARCH}-debian-11.tar.gz aspnet-core-3.1.29-0-linux-${OS_ARCH}-debian-11.tar.gz.sha256
RUN apt-get update && apt-get upgrade -y && \
    apt-get clean && rm -rf /var/lib/apt/lists /var/cache/apt/archives
RUN sed -i 's/^PASS_MAX_DAYS.*/PASS_MAX_DAYS    90/' /etc/login.defs && \
    sed -i 's/^PASS_MIN_DAYS.*/PASS_MIN_DAYS    0/' /etc/login.defs && \
    sed -i 's/sha512/sha512 minlen=8/' /etc/pam.d/common-password

COPY rootfs /
RUN /opt/bitnami/scripts/aspnet-core/postunpack.sh
ENV APP_VERSION="3.1.29" \
    BITNAMI_APP_NAME="aspnet-core" \
    DOTNET_CLI_HOME="/app" \
    DOTNET_ROOT="/opt/bitnami/aspnet-core/bin" \
    PATH="/opt/bitnami/aspnet-core/bin:$PATH"

WORKDIR /app
ENTRYPOINT [ "/opt/bitnami/scripts/aspnet-core/entrypoint.sh" ]
CMD [ "/bin/bash" ]
