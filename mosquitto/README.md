*Docker file to get started

To build, put both `Dockerfile` and `docker-entrypoint.sh` in the same (empty, unless you know what you're doing) folder. Make sure you give enough permissions to the `docker-entrypoint.sh` (I gave 777, probably overkill. I might fine tune later).

In the directory with the files, run `docker build` with whatever arguments you'd like (I did `docker build -t aephir/mosquitto:0.1.0 -t aephir/mosquitto:latest .`)

After that, you can either `docker run` or use a `docker-compose.yaml`. This is what I use, and what I have provided an example of. Make sure you have the directories needed. In the example above, I have a `/home/aephir/docker/mosquitto` directory, the `config`, `data`, `log` are then created within created.

Make sure you change you add/change a `mosquitto.conf` file.

Take a look [here](https://github.com/eclipse/mosquitto/tree/master/docker/1.4.14) and [here](https://hub.docker.com/_/eclipse-mosquitto/) for more information
