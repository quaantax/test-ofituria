# Ofituria test

## El stack incluye
* php-fpm
* Node.js
* MySQL
* Nginx

## Instalación inicial

1. Clonar el repositorio.

```bash
$ git clone 
```

2. Instalación inicial.

```bash
$ cd docker-laravel-vue
$ make init
```

3. Instalar y compilar paquetes npm en los contenedores

```bash
$ cd docker-laravel-vue
$ make node
$ yarn install
$ yarn dev
```
4. Cambiar el host y el puerto de la BBDD para poder hacer la migración

```bash
DB_HOST=127.0.0.1
DB_PORT=33060
```

5. Ejecutamos el siguiente comando para llenar la BBDD con datos

php artisan migrate:fresh --seed --seeder=ProductSeeder

6. Cambiamos el host y el puerto de la BBDD para que funcionen las llamadas desde el front (Habrá que poner la IP con la que se haya creado el contenedor de mysql)

```bash
DB_HOST=XXX.X.X.X
DB_PORT=3306
```

7. Añadir a `/etc/hosts`.

```bash
127.0.0.1 docker-laravel-vue.work
127.0.0.1 api.docker-laravel-vue.work
```

8. Acceso a Laravel y Vue.

* Laravel 

    http://api.docker-laravel-vue.work

* Vuejs 

    http://docker-laravel-vue.work
