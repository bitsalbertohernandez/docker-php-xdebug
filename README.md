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
-  Luego en el navegador teclear **localhost**.
### Directorios de configuraciones
------------
- XDEBUG -> /config/php-fpm/xdebug-ini-overrides.ini
- PHP.INI -> /config/php-fpm/php-ini-overrides.ini
- HOST VIRTUALES -> /config/nginx/nginx.conf

### Instalando Drush:
------------
- Correr el comando que aparece a continuación y esperar a que termine de descargar la imagen, al finalizar mostrará en la consola los comandos de Drush. La imagen la descarga solo la primera vez que ejecutas el comando.
```sh
docker run --rm -it -v $PWD/web:/app/<DIRECTORIO DE TU DRUPAL> drush/drush:9
```
- Crea un alias donde guardar el comando, así a fututo no tengas que colocar todo eso, para el caso de Mac y Linux el alias quedaría así.
```sh
alias drush='docker run --rm -it -v $PWD/web:/app/<DIRECTORIO DE TU DRUPAL> drush/drush:9'
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
                "/app/web": "${workspaceFolder}/web/<DIRECTORIO A TU PROYECTO>"
            }
    }
  ]
}
```