Con este comando instalamos el motor de Docker. Para esto necesitaremos hacer unos pasos previos:

```
sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

Anadimos la GPG key oficial de Docker:

```
sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

Seteamos el repositorio:

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
```

Una vez hecho esto, ya habremos instalado las dependencias y estaremos listos para instalar el motor de Docker.

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

Luego, deberemos descargar el siguiente [archivo](https://desktop.docker.com/linux/main/amd64/docker-desktop-4.12.0-amd64.deb?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-linux-amd64) para poder instalar docker-desktop de la siguiente manera:

```
sudo apt install ./docker-desktop-4.12.0-amd64.deb
```

Luego, pondremos los siguientes comandos para eliminar la necesidad de poner `sudo` por cada interaccion que tengamos con docker

```
sudo usermod -aG docker $USER

newgrp docker
```

Una vez hecho esto, necesitaremos crear un archivo, el cual llamaremos `docker-compose.yml` y dentro del mismo pondremos lo siguiente:

```yml
version: "2"
services:
  # MongoDB: https://hub.docker.com/_/mongo/
  mongodb:
    image: mongo:4.2
    networks:
      - graylog
    #DB in share for persistence
    volumes:
      - /mongo_data:/data/db
    # Elasticsearch: https://www.elastic.co/guide/en/elasticsearch/reference/7.10/docker.html
  elasticsearch:
    image: docker.elastic.co/elasticsearch/elasticsearch-oss:7.10.2
    #data folder in share for persistence
    volumes:
      - /es_data:/usr/share/elasticsearch/data
    environment:
      - http.host=0.0.0.0
      - transport.host=localhost
      - network.host=0.0.0.0
      - "ES_JAVA_OPTS=-Xms512m -Xmx512m"
    ulimits:
      memlock:
        soft: -1
        hard: -1
    mem_limit: 1g
    networks:
      - graylog
  # Graylog: https://hub.docker.com/r/graylog/graylog/
  graylog:
    image: graylog/graylog:4.3
    #journal and config directories in local NFS share for persistence
    volumes:
      - /graylog_journal:/usr/share/graylog/data/journal
    environment:
      # CHANGE ME (must be at least 16 characters)!
      - GRAYLOG_PASSWORD_SECRET=ultrasecretpassword
      # Password: admin
      - GRAYLOG_ROOT_PASSWORD_SHA2=SHA2_de_ultrasecretpassword
      - GRAYLOG_HTTP_EXTERNAL_URI=http://localhost:9000/
    entrypoint: /usr/bin/tini -- wait-for-it elasticsearch:9200 --  /docker-entrypoint.sh
    networks:
      - graylog
    links:
      - mongodb:mongo
      - elasticsearch
    restart: always
    depends_on:
      - mongodb
      - elasticsearch
    ports:
      # Graylog web interface and REST API
      - 9000:9000
      # Syslog TCP
      - 1514:1514
      # Syslog UDP
      - 1514:1514/udp
      # GELF TCP
      - 12201:12201
      # GELF UDP
      - 12201:12201/udp
# Volumes for persisting data, see https://docs.docker.com/engine/admin/volumes/volumes/
volumes:
  mongo_data:
    driver: local
  es_data:
    driver: local
  graylog_journal:
    driver: local
networks:
  graylog:
    driver: bridge
```

Dentro de este archivo, tendremos que modificar 3 parametros:

- GRAYLOG_PASSWORD_SECRET: setearemos una contrasena de minimo 16 caracteres
- GRAYLOG_ROOT_PASSWORD_SHA2: para este paremetro, correremos el comando que se encuentra abajo y pondremos la misma contrasena que usamos en el paso anterior. Esto generara una clave SHA2 la cual pondremos para este parametro.
- GRAYLOG_HTTP_EXTERNAL_URI: link de nuestro server, pero dado que trabajaremos en local usaremos localhost

Comando para el **GRAYLOG_ROOT_PASSWORD_SHA2**:

```
echo -n "Enter Password: " && head -1 </dev/stdin | tr -d '\n' | sha256sum | cut -d" " -f1
```

Una vez configurado el archivo, correremos el siguiente comando para virtualizar los 3 contenedores, que van a contener a Graylog, Mongo y ElasticSearch.

```
docker-compose up
```

> Se le puede agregar la flag **-d** (va al final) que sirve para que podamos seguir utilizando la consola en caso de que lo quisieramos.

Una vez hecho esto, ingresaremos a la URL que definimos anteriormente. En el login insertaremos como usuario `admin` y de contrasena rellenaremos con la password seteada anteriormente en **GRAYLOG_PASSWORD_SECRET**.
