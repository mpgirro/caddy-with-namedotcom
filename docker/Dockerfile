FROM caddy:2.8.4-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/namedotcom

FROM caddy:2.8.4

COPY --from=builder /usr/bin/caddy /usr/bin/caddy

# Overwrite the OCI Image Specification source label to enable tools 
# like Renovate and Dependabot to automatically provide release notes.
LABEL org.opencontainers.image.source="https://github.com/caddyserver/caddy"
