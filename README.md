### Esta imagen contiene:
------------ 
* PHP 7.4

* NGINX server

* Mariadb

* Xdebug 2.9.4

* Drush

* Git

* Composer

* CodeSniffer

### Pasos para correr la imagen 
------------   
- Instalar Docker y Docker Compose  
- git clone https://github.com/bitsalbertohernandez/docker-php-xdebug.git .
- En el directorio del proyecto ejecutar el comando **docker-compose up -d** y esperar que termine el proceso de descarga y configuración de las imagenes.
- Luego en el navegador teclear **localhost**.

### Directorios de configuraciones
------------
- XDEBUG -> /config/php-fpm/xdebug-ini-overrides.ini
- PHP.INI -> /config/php-fpm/php-ini-overrides.ini
- HOST VIRTUALES -> /config/nginx/nginx.conf  
- 
###  Ejecutar Drush:
------------
- En el directorio donde se encuentra el archivo **docker-compose.yml** ejecutar el comando:
```sh
docker-compose exec php-fpm /bin/bash
```
- Una vez ejecutado el comando estaras dentro de la imagen que contiene el drush con cd /**directorioatuproyecto**  te mueves a la raíz del proyecto y ejecutas el comando drush
- Si no quieres colocar siempre el comando grande puedes crear un alias, siendo el ejemplo como se haría para **MAC** y **Linux**
```sh
alias nombredelalias='docker-compose exec php-fpm /bin/bash'
``` 
### VSCODE config para XDEBUG  
------------
```
{

"version": "0.2.0",
"configurations": [
{
"name": "Listen for XDebug",
"type": "php",
"request": "launch",
"port": 9000,
"pathMappings": {
"/app/web/DIRECTORIO_A_LA_RAIZ_DEL_PROYECTO": "${workspaceRoot}"
}
}
]
}
```