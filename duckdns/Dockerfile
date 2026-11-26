# Base image updated by Renovate, update versionCompatibility on Alpine base bump
ARG BUILD_FROM=ghcr.io/home-assistant/base:3.24-2026.11.1@sha256:5021aac8a4b7f2a1397e23a9749dfe9f736463ffa471df6b200216c68d530fe6
FROM $BUILD_FROM

# Setup base
ARG DEHYDRATED_VERSION=0.8.0
RUN apk add --no-cache openssl \
  && curl -s -o /usr/bin/dehydrated \
    "https://raw.githubusercontent.com/Xebozone/dehydrated/${DEHYDRATED_VERSION}/dehydrated" \
  && chmod a+x /usr/bin/dehydrated

# Copy root filesystem 
COPY rootfs /

LABEL \
    org.opencontainers.image.title="Home Assistant App: Duck DNS" \
    org.opencontainers.image.description="Free Dynamic DNS (DynDNS or DDNS) service with Let's Encrypt support" \
    org.opencontainers.image.source="https://github.com/home-assistant/app-duckdns" \
    org.opencontainers.image.licenses="Apache License 2.0"
