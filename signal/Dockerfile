ARG BUILD_FROM
# hadolint ignore=DL3006
FROM bbernhard/signal-cli-rest-api:0.70

COPY options.sh /options.sh

RUN ["chmod", "+x", "/options.sh"]

RUN apt-get clean \

        && apt-get update \

        && apt-get install -y --no-install-recommends jq

WORKDIR /data/data/

ENTRYPOINT ["/options.sh"]

VOLUME ["/data"]

# Build arugments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="Signal Messenger" \
    io.hass.description="Signal Messenger" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.version="${BUILD_VERSION}" \
    io.hass.type="addon" \
    maintainer="theblackmini" \
    org.label-schema.description="Signal Messenger" \
    org.label-schema.build-date="${BUILD_DATE}" \
    org.label-schema.name="Nextcloud" \
    org.label-schema.schema-version="${BUILD_VERSION}" \
    org.label-schema.url="https://github.com/theblackmini/signal-addon" \
    org.label-schema.usage="https://github.com/theblackmini/signal-addon" \
    org.label-schema.vcs-ref="${BUILD_REF}" \
    org.label-schema.vcs-url="https://github.com/theblackmini/" \
    org.label-schema.vendor="No Vendor"
