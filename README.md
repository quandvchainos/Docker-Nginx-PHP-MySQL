*Pre-requisites
    - Nginx: 1.19.2
    - PHP: 7.4-fpm
    - MariaDB: 10.5.5
    - Composer
    - Nodejs 12.18.x & npm 6.14.x
    - Redis
    - Make
* Docker Command
    - Start: docker-compose up -d
    - Stop: docker-compose down
    - Re-build: docker-compose up --d --build app
==========
Build image
-----------

```bash
git clone https://github.com/andreal01/Docker-Nginx-PHP-MySQL.git
cd Docker-Nginx-PHP-MySQL

```

Run on container
-------------
```bash
sudo make run
```
