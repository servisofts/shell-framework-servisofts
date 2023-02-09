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
Required curl for this install.

```bash
cd /opt/ && sudo curl -O https://repo.servisofts.com/opt/sfs/sfs-latest.installer && sudo bash sfs-latest.installer
```


```bash
rickypazd@Ricardos-MacBook-Pro ~ % sfs -h
Usage: sfs  [OPTIONS] [COMMANDS].

Options:
  -h                Muestra la ayuda.
  --help            Muestra la ayuda.
  -v                Muestra la version de sfs.
  --version         Muestra la version detallada de sfs.

Commands:
  link              Crea un link simbolico de del proyecto en el que nos encontramos.
  unlink            --
  publish           --
  clean             Limpiar los archivos de compilacion.
  repo              --
  install           Instala un packete sfs desde el repositorio.
  uninstall         --
  build             Compila el proyecto encontrado en la ruta que nos encontramos.
  create            Crea un nuevo projecto en el directorio donde nos encontramos.

Run 'sfs COMMAND --help' for more information on a command.
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




# DEVELOP

1. Download repository from `https://github.com/servisofts/shell-framework-servisofts`;
2. Verificar la ayuda.
```bash
./src/sfs -h
```
3. Para instalar el codigo con un sinLink y poder desarrollar.
```bash
sudo ./src/sfs link

```
1. Para desinstalar el sinLink.
```bash
sudo ./src/sfs unlink
```