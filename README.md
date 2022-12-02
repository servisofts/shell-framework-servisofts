# Shell Framework Servisofts
#### by Ricardo Paz Demiquel

- Nombre: sfs
- Version: 1.0


## VARIABLES
- `NAME` Nombre del script.
- `VERSION` Version del cript.
- `ENV_FILE=` Direccion del archibo de configuracion 

## STATICS
- `DIR_PATH` Direccion absoluta del script.
- `DIR_SFS` Direccion absoluta del sfs.
- `FOLDER_NAME` Nombre del folder donde se ejecuto el script.
- `PARAMS` Parametros de entrada tipo array.
- `PARAMS_STR` Parametros de entrada tipo string.



# INSTALL

## Estandar

```bash
cd /opt/ && sudo curl -O https://repo.servisofts.com/opt/sfs/sfs-latest.installer && sudo bash sfs-latest.installer
```

## Docker
```dockerfile
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
```




# For Mac
```bash
#Install homebrew first.

ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" < /dev/null 2> /dev/null
Install shc.

brew install shc
```
