FROM alpine:3.16

WORKDIR /usr/src/servisofts
RUN apk update
RUN apk upgrade
RUN apk add bash
RUN apk add perl
RUN apk add --update curl
RUN rm -rf /var/cache/apk/*

ARG SKERNEL_VERSION=1.2.1
RUN cd /opt/ \
    && curl -O https://repo.servisofts.com/opt/skernel/$SKERNEL_VERSION/skernel-$SKERNEL_VERSION.installer \
    && bash skernel-$SKERNEL_VERSION.installer

COPY . .

CMD ["bash", "start.sh"]
