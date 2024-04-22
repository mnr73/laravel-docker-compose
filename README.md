<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" height="100" alt="Laravel Logo"></a><img src="https://cdn.worldvectorlogo.com/logos/docker.svg" height="100" alt="Laravel Logo"></p>

## About this Laravel fresh repo

this laravel repo provide simple docker files and docker compose to run Laravel for develop and production purpose.
this repo is contain three docker compose files.

- docker-compose-common.yml : the base of docker compose files
- docker-compose-prd.yml : docker compose file for production
- docker-compose.yml : docker compose file for development in local

to work with this docker compose files you need docker base knowledge.

docker files placed in /mnr_docker directory.

in additional add [Laravel ide helper](https://github.com/barryvdh/laravel-ide-helper) package and put some setting for auto generate files. for auto generate files you need this [run on save](https://marketplace.visualstudio.com/items?itemName=emeraldwalk.RunOnSave) extension for vsCode.

## How to use

- step 1: clone repo
- step 2 (optional): you can remove /.git directory and initial repo again
- step 3: cp .env.example to .env
- step 4: the default database in .env file is sqlite if you want continue to use taht you can comment or remove mysql and phpMyAdmin services in docker compose files. or change DB_CONNECTION value to mysql in .env file. change env file like below lines to use mysql. if you want user other databases you should change docker compose files.

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=password
```

- step 5: change other env variable if you need and run `docker compose up -d`
- step 6: run `docker compose exec -it -u 1000 laravel composer install`
- step 7: run `docker compose exec -it -u 1000 laravel php artisan key:generate`
- step 8: run `docker compose exec -it -u 1000 laravel php artisan migrate`
- step 9: open [localhost](http://localhost) to see laravel welcome page
