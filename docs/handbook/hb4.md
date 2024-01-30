---
sidebar_label: 'Linux - Gestión externa de SSL'
title: 'Linux - Gestión externa de SSL'
--- 

# Instalación del Facturador

## Descripción 

Este tutorial simplifica la instalación en Linux, destacando la opción de omitir SSL inicialmente. Los pasos incluyen la edición de parámetros en un archivo, la limpieza de caché, y la advertencia sobre la necesidad de configurar SSL para el acceso completo. Una guía práctica y directa para usuarios de Ubuntu 18+.

## Pasos

1. Para instalar debe ejecutar el script evitando instalar el SSL, le será consultado en el proceso y deberá ingresar "n"

2. Finalizada la instalación debe dirigirse a la ruta de instalación
    ~~~
    cd /root/facturadorpro31/
    ~~~

3. debe editar el archivo __`.env`__
    ~~~
    nano .env
    ~~~
    _dentro del editor ubicar los parámetros y cambiarlos_

    **Antes:**

    ```ini
    APP_URL=https://${APP_URL_BASE}
    FORCE_HTTPS=false
    ```

    **Después:**

    ```ini
    APP_URL=http://${APP_URL_BASE}
    FORCE_HTTPS=true
    ```

4. Una vez finalizado, guarde y salga del editor

5. Ejecute los siguientes comandos para eliminar la caché de la aplicación
    ~~~
    php artisan config:Cache
    ~~~

6. Con eso habrá completado el lado de la herramienta, en ese momento hasta no tener un SSL configurado no podrá acceder a la herramienta


:::warning
Recuerde habilitar el puerto 443 para poder tener acceso a la herramienta.
:::
