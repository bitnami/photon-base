FROM photon:3.0
LABEL maintainer "Bitnami <containers@bitnami.com>"
ENV IMAGE_OS=photon-3

COPY rootfs /

RUN tdnf remove toybox -y && \
    tdnf upgrade -y && \
    install_packages tar gzip sudo procps-ng libaio-devel which shadow sed findutils gawk

RUN useradd -ms /bin/bash bitnami && groupadd bitnami && usermod -g bitnami bitnami && \
    mkdir -p /opt/bitnami && chown bitnami:bitnami /opt/bitnami && \
    sed -i -e 's/\s*Defaults\s*secure_path\s*=/# Defaults secure_path=/' /etc/sudoers && \
    echo "bitnami ALL=NOPASSWD: ALL" >> /etc/sudoers

# The following security actions are recommended by some security scans.
# https://console.bluemix.net/docs/services/va/va_index.html
RUN sed -i 's/^PASS_MAX_DAYS.*/PASS_MAX_DAYS    90/' /etc/login.defs && \
    sed -i 's/^PASS_MIN_DAYS.*/PASS_MIN_DAYS    1/' /etc/login.defs

ENV BITNAMI_IMAGE_VERSION=3-r135

ENTRYPOINT ["/entrypoint.sh"]
