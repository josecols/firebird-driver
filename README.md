Laravel Firebird driver
=======================

Driver para Laravel que soporta conexiones con bases de datos Firebird.


Instalación
------------
Para instalar el driver en tu aplicación de Laravel 4.2 se debe incluir el siguiente JSON en el archivo `composer.json` ubicado en la raíz de Laravel.

```json
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/josecols/firebird-driver"
    }
],
require {
  "josecols/firebird-driver": "dev-master"
}
```

Y ejecuta el siguiente comando en la terminal.

`composer update`

Esto va a descargar e instalar la última versión disponible de este repositorio.

Una vez hecho esto, en el directorio `app/config` de tu aplicación Laravel abre `app.php` busca `'Illuminate\Database\DatabaseServiceProvider',` y reemplazala por `'Ccovey\ODBCDriver\ODBCDriverServiceProvider',`

Finalmente indica a Laravel que el driver que deseas utilizar es el de Firebird, en el archivo `config/database.php` de la siguiente forma.

```php
'default' => 'firebird',
    'connections' => array(
        'firebird' => array(
            'driver' => 'odbc',
            'dsn' => 'host=127.0.0.1;dbname=<ruta al archivo de la base de datos>;',
            'grammar' => 'DB2',
            'username' => 'SYSDBA',
            'password' => 'masterkey',
            'database' => '/<ruta al archivo de la base de datos>',
        ),
    ),
```
