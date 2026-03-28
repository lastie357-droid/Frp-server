FROM alpine:latest

RUN apk add --no-cache wget \
    && wget -q https://github.com/fatedier/frp/releases/download/v0.61.1/frp_0.61.1_linux_amd64.tar.gz \
    && tar -xzf frp_0.61.1_linux_amd64.tar.gz \
    && mv frp_0.61.1_linux_amd64/frps /usr/local/bin/frps \
    && rm -rf frp_0.61.1_linux_amd64*

COPY frp/frps.toml /etc/frp/frps.toml

EXPOSE 7000 7500 6000 5555

CMD ["frps", "-c", "/etc/frp/frps.toml"]
