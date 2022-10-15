[![CodeFactor](https://www.codefactor.io/repository/github/redfrogsss/selfremind/badge)](https://www.codefactor.io/repository/github/redfrogsss/selfremind)
# SelfRemind
a selfhosted To-do List Manager built with [Next.js](https://nextjs.org/), [Chakra-UI](https://chakra-ui.com/) and [MySQL](https://www.mysql.com/).

## Screenshots
![Alt text](./readme-img/login.png "Login Page")
![Alt text](./readme-img/home.png "Home Page")

## Getting Started with `docker-compose`

To start with, you must install [Docker](https://www.docker.com/products/docker-desktop) and [docker-compose](https://docs.docker.com/compose/) on your computer.

First, create a `docker-compose.yml` file with the following content:

```yml
version: "3"
services:
  web:
    build: .
    ports:
      - "3000:3000"
    restart: unless-stopped
  db:
    image: mysql/mysql-server:8.0
    restart: unless-stopped
    command: --default-authentication-plugin=mysql_native_password
    environment:
      MYSQL_ROOT_PASSWORD: example
      MYSQL_DATABASE: selfremind
      MYSQL_USER: selfremind
      MYSQL_PASSWORD: selfremind123
    volumes:
      - dbdata:/var/lib/mysql
      - ./my.conf:/etc/mysql/my.cnf
volumes:
  dbdata:
```

Then, run the command to start the server:
```bash
docker-compose up -d
```

Wait a minutes and open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

By default, the username is `admin` and the password is `admin`.

