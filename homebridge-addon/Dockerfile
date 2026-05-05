ARG BUILD_FROM
FROM ${BUILD_FROM}

# Labels
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION

LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Fred" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}

# Copy root filesystem
COPY rootfs /

# Set environment variables for Homebridge
ENV HOMEBRIDGE_CONFIG_UI=1
ENV HOMEBRIDGE_CONFIG_UI_PORT=8581
ENV UIX_CUSTOM_PLUGIN_PATH=/homebridge/node_modules
ENV USER=root
ENV HOME=/homebridge

# Expose Homebridge UI port
EXPOSE 8581

# Use host network for mDNS/Bonjour (required for HomeKit discovery)
# This is set in config.yaml with host_network: true
