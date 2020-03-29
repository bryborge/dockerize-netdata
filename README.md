# Netdata (Dockerized)

This is a project that puts
[Netdata](https://www.netdata.cloud/)
inside a container and is specifically designed to work with
[this](https://github.com/sonofborge/dockerize-traefik) Traefik project.

## Requirements

*   [Docker](https://docs.docker.com/install/)
*   [Docker Compose](https://docs.docker.com/compose/install/)
*   A linux box to deploy to ;)

## Up and Running

1.  Pull down the repo and change into the project directory

    ```sh
    git clone https://github.com/sonofborge/dockerize-netdata.git netdata && cd netdata
    ```

1.  Create and modify `.env` for your needs.

    ```sh
    cp .env.example .env
    ```

1.  Generate a user/password hash with `htpasswd` and store the output in `config/usersfile`.

    ```sh
    htpasswd -nB $USER
    ```

1.  Run Docker Compose

    ```sh
    docker-compose up -d
    ```

If all went well,
you should now be running Netdata inside a container behind your
[Traefik reverse proxy](https://github.com/sonofborge/dockerize-traefik).
