FROM electriccoinco/zcashd-build:debian10

RUN apt-get update && \
    apt-get install -y \
      jq zip

ARG GO_IPFS_VERSION=v0.6.0
ARG RCLONE_VERSION=v1.51.0
RUN curl -LO https://dist.ipfs.io/go-ipfs/${GO_IPFS_VERSION}/go-ipfs_${GO_IPFS_VERSION}_linux-amd64.tar.gz \
    && tar zxf go-ipfs_${GO_IPFS_VERSION}_linux-amd64.tar.gz \
    && cp go-ipfs/ipfs /usr/local/bin/ipfs \
    && rm -Rf go-ipfs_$GO_IPFS_VERSION_linux-amd64.tar.gz \
    && curl -L https://dl.min.io/client/mc/release/linux-amd64/mc -o /usr/local/bin/mc \
    && chmod +x /usr/local/bin/mc \
    && curl -LO https://downloads.rclone.org/${RCLONE_VERSION}/rclone-${RCLONE_VERSION}-linux-amd64.zip \
    && unzip rclone-${RCLONE_VERSION}-linux-amd64.zip \
    && cp rclone-${RCLONE_VERSION}-linux-amd64/rclone /usr/local/bin/rclone \
    && chmod +x /usr/local/bin/rclone \
    && rm rclone-${RCLONE_VERSION}-linux-amd64.zip
