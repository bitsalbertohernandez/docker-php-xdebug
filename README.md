### Esta imagen contiene:
------------

* PHP 7.4
* NGINX server 
* Mariadb
* Xdebug 2.9.4
###  Pasos para correr la imagen

------------


-  Instalar Docker y Docker Compose

-  git clone https://github.com/bitsalbertohernandez/docker-php-xdebug.git .
-  En el directorio del proyecto correr el comando **docker-compose up -d** y esperar que termine el proceso de descarga y configuración de las imagenes.
-  Luego en el navegador teclear **localhost** .
### Directorios de configuraciones
------------
- XDEBUG -> /config/php-fpm/xdebug-ini-overrides.ini
- PHP.INI -> /config/php-fpm/php-ini-overrides.ini
- HOST VIRTUALES -> /config/nginx/nginx.conf
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
                "/app/web": "${workspaceFolder}/web/<DIRECTORIO A TU PROYECTO>"
            }
    }
  ]
}
```