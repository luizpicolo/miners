FROM alpine:latest

ARG XMRIG_VERSION
ARG WALLET_ADDRESS
ARG COIN_PREFIX
ARG WORKER_NAME

RUN apk add --no-cache wget tar

RUN mkdir /xmrig
WORKDIR /xmrig

RUN wget https://github.com/xmrig/xmrig/releases/download/v${XMRIG_VERSION}/xmrig-${XMRIG_VERSION}-linux-static-x64.tar.gz && \
    tar xf xmrig-${XMRIG_VERSION}-linux-static-x64.tar.gz && \
    rm xmrig-${XMRIG_VERSION}-linux-static-x64.tar.gz

WORKDIR /xmrig/xmrig-${XMRIG_VERSION}

ENV COIN_PREFIX=${COIN_PREFIX}
ENV WALLET_ADDRESS=${WALLET_ADDRESS}
ENV WORKER_NAME=${WORKER_NAME}

CMD ["sh", "-c", "./xmrig -a rx -o stratum+ssl://rx.unmineable.com:443 -u ${COIN_PREFIX}:${WALLET_ADDRESS}.${WORKER_NAME} -p x"]