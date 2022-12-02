FROM alpine:3.16

WORKDIR /usr/src/servisofts
RUN apk update
RUN apk upgrade
RUN apk add bash
RUN apk add perl
RUN apk add --update curl
RUN rm -rf /var/cache/apk/*

ARG SFS_VERSION=1.0.4
RUN cd /opt/ \
    && curl -O https://repo.servisofts.com/opt/sfs/$SFS_VERSION/sfs-$SFS_VERSION.installer \
    && bash sfs-$SFS_VERSION.installer

RUN sfs install example
COPY . .

CMD ["bash", "start.sh"]
