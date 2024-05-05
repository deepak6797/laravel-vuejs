# To run LARAVEL_APP
# Make sure docker and docker-compose is installed on the system

1. Create a .env file
    LARAVEL_DATABASE=GiveValue
    LARAVEL_PASSWORD=GiveValue

2. Assign port according to system free ports

3. To run database migration
    docker-compose exec php-app php artisan migrate

4. Inside "src" directory within file .env configure database
    DB_CONNECTION=mysql
    DB_HOST=mysql-app
    DB_PORT=3306
    DB_DATABASE=GiveValue
    DB_USERNAME=root
    DB_PASSWORD=GiveValue
# Here DB_HOST is the service name defined in the docker-compose 

5. To run

    First -> docker-compose up -d --build or docker-compose build
    Second -> docker-compose up -d

6. To stop
    docker-compose down

7. To access
    - Go in chrome or any browser
    - Type ip-address or localhost with exposed port of nginx like ip:port or localhost:7777

8. If vendor and node_modules directory are not found or it gives error
    - Delete the vendor or node_modules
    - Ensure docker containers are running (docker ps)
    - To create vendor directory run -> docker-compose exec php-app composer install
    - To create node_modules directory run -> docker-compose exec php-app npm install

# fastcgi_pass php-laravel:9000;: This directive specifies the address and port of the PHP-FPM server that will handle PHP processing. Requests for PHP files will be forwarded to this server for execution.

# php-laravel -> service defined in docker-compose