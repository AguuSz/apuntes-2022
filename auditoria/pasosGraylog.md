Con este comando instalamos el motor de Docker.

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

Luego con este otro comando instalamos docker

```
sudo apt install ./docker-desktop-4.11.1-amd64.deb
```

Luego ejecutamos estos comandos para instalar los requerimientos de nuestro server de prueba:

```
sudo docker pull graylog/graylog:4.2-jre11
sudo docker pull mongo
sudo docker pull docker.elastic.co/elasticsearch/elasticsearch:8.4.1-arm64
```
