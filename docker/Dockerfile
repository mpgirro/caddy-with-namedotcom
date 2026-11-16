FROM caddy:2.11.6-builder AS builder

# caddy-dns/namedotcom pins libdns/namedotcom v0.3.3, which predates libdns v1 and no longer compiles
RUN xcaddy build \
    --with github.com/caddy-dns/namedotcom \
    --with github.com/libdns/namedotcom@v0.9.0

FROM caddy:2.11.6

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
