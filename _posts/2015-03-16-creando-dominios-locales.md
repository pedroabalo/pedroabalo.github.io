---
title:  "Creando dominios en local"
categories: 
    - development
tags:
    - Tomcat
    - Apache
    - hosts
---

## Objetivo
Utilizar un dominio fake en local (example.com) en vez de http://localhost:8080 en un contendor Tomcat y un servidor Apache

### Paso 1. Editando hosts

Editar el fichero /etc/hosts y añadir nuestro dominio local

$sudo vi /etc/hosts

Añadiendo la siguiente linea al fichero

127.0.0.1       example.com

### Paso 2. Añadir virtualhost a Apache

Acceder a /etc/apache2/sites-available (como administrador) y crear el fichero example.com.conf

$ cd /etc/apache2/sites-available

$ sudo vi example.com.conf 

Añadir las siguientes líneas al fichero recién creado:

<VirtualHost *:80>
ProxyPreserveHost On
ProxyRequests Off
ServerName http://www.example.com
ServerAlias example.com
ProxyPass / http://localhost:8080/myapp/
ProxyPassReverse / http://localhost:8080/myapp/
ErrorLog logs/example.com-error_log
CustomLog logs/example.com-access_log combined
</VirtualHost>

### Paso 3. Habilitar la configuración


Ahora tendremos que habilitar la configuración en sites-enabled 

$ cd /etc/apache2/example.com.conf
$ sudo a2ensite example.com.conf
$ sudo service apache2 reload

Es posible que os de errores en el fichero de log (crear la carpeta logs en apache)

$ sudo mkdir /etc/apache2/logs

En caso de que os de errores en los módulos de proxy, cargar el módulo en apache (y otros que os vaya pidiendo al reiniciar el apache)

$ sudo a2enmod proxy

Y volver a reiniciar apache2

$ sudo service apache2 restart

