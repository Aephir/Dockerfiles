# Docker file to get started with mosquitto broker and clients

To build, put both `Dockerfile` and `docker-entrypoint.sh` in the same (empty, unless you know what you're doing) folder. Make sure you give enough permissions to the `docker-entrypoint.sh` (I gave 777, probably overkill. I might fine tune later).

In the directory with the files, run `docker build` with whatever arguments you'd like. I used:

```
docker build -t aephir/mosquitto:0.1.0 -t aephir/mosquitto:latest .
```
This is what is assumed in the rest of this guide, and the other files herein.

After that, you can either `docker run` or use a `docker-compose.yaml`. This is what I use, and what I have provided an example of. Make sure you have the directories needed. In the example above, I have a `/home/aephir/docker/mosquitto` directory, the `config`, `data`, `log` are then created upon run.

Make sure you change you add/change a `mosquitto.conf` file.

Take a look [here](https://github.com/eclipse/mosquitto/tree/master/docker/1.4.14) and [here](https://hub.docker.com/_/eclipse-mosquitto/) for more information about the docker container (the primary inspiration for this one), and [here](https://mosquitto.org/) for more general information about mosquitto. [Here](https://hub.docker.com/r/aephir/mosquitto/) is the docker hub page for this.

This is provided as is, with no guarantees. It is the users responsibility to obey any restrictions placed on anything, based on the software used.

_____
To push to hub.docker.com

```
docker login
docker push aephir/mosquitto:latest
```
