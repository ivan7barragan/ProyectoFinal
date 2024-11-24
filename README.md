# Laravel Notas de Compras con Sistema CRUD

Un sistema de gestión de notas compras desarrollado en Laravel que incluye CRUD, autenticación, y estilos con Bootstrap.

#Video Explicativo

https://github.com/user-attachments/assets/7af1d9c1-077e-4960-aacb-0689bd73eaca

## Requisitos Previos

Antes de comenzar, asegúrate de tener instalados los siguientes componentes:

- **PHP 8.3 o superior** con la extensión MySQL.
- **Composer** (gestor de dependencias de PHP).
- **Node.js** con `npm` y `nvm` instalado.
- **MySQL** o cualquier base de datos compatible con Laravel.
- **Git** (opcional pero recomendado).

## Instalación

Sigue los pasos a continuación para instalar y configurar el proyecto:

### 1. Clonar el Proyecto.

```bash 
git clone https://github.com/ivan7barragan/ProyectoFinal/
cd ProyectoFinal/
```
### 2. Configurar el Entorno

Abre y edita el archivo `.env` para configurar las credenciales de tu base de datos y otros parámetros de entorno:

```bash
vim .env
```

Asegúrate de que el archivo tenga los valores correctos, por ejemplo:

```.env
DB_CONNECTION=mysql 
DB_HOST=127.0.0.1 
DB_PORT=3306 
DB_DATABASE=crud_compras 
DB_USERNAME=root 
DB_PASSWORD=your_password
```
### 3. Crear el Modelo y la Migración

Genera un modelo llamado `Product` junto con su archivo de migración:

```bash
php artisan make:model Product -m
```

Edita el archivo de migración para definir la estructura de la tabla `products`:

```bash
cd database/migrations/ 
vim 2024_11_24_042208_create_products_table.php
```

Asegúrate de que la estructura sea algo como esto:

```php
$table->id(); 
$table->string('description'); 
$table->double('price'); 
$table->unsignedInteger('stock'); 
$table->timestamps();
```

Luego ejecuta las migraciones:

```bash
php artisan migrate
```
### 4. Generar la Llave de Aplicación

Ejecuta el comando para generar la clave única de tu aplicación:

```bash
php artisan key:generate
```
### 5. Instalar Dependencias de Composer

```bash
composer install 
composer update 
```
### 6. Instalar Laravel UI y Bootstrap

```bash
composer require laravel/ui 
php artisan ui bootstrap 
php artisan ui bootstrap --auth
```

Esto generará el scaffolding de autenticación y los recursos de Bootstrap.
### 7. Configurar Node.js y NVM

Instala `nvm` y utiliza Node.js versión 22:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.0/install.sh | bash 
nvm install 22
```
### 8. Instalar Extensión de MySQL para PHP

Asegúrate de que la extensión de MySQL esté instalada para PHP:

```bash
sudo apt-get install php8.3-mysql
```
### 9. Instalar el Generador de CRUD

Instala el paquete `ibex/crud-generator`:

```bash
composer require ibex/crud-generator --dev 
php artisan vendor:publish --tag=crud
```

Genera un CRUD para la entidad `products`:

```bash
php artisan make:crud products
```
### 10. Compilar Recursos Frontend

Instala las dependencias de `npm` y compila los activos:

```bash
npm install && npm run dev
```
### 11. Iniciar el Servidor

Ejecuta el servidor de desarrollo de Laravel:

```bash
php artisan serve
```

Accede a la aplicación en tu navegador en `http://127.0.0.1:8000

-------------
