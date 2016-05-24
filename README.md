Symfony App with PostgreSQL Driver
=====

Tags
----

 - PHP 5.6: `webridge/symfony-app:php56`
 - PHP 7.0: `webridge/symfony-app:php70`

Basic Usage
-----------

```
docker run -d -v $(pwd):/var/app \
    -p 8080:80 \
    webridge/symfony-app
```

Linking a Database
------------------

```
docker run -d -v $(pwd):/var/app \
    --link your_db:db \
    -p 8080:80 \
    webridge/symfony-app
```


Basic Setup Example
-------------------

```
docker run -d --name sample_db postgres

docker run --rm \
    -v $(pwd):/app \
    -v YOUR_COMPOSER_CACHE:/root/.composer \
    -e COMPOSER_HOME=/root/.composer \
    -e SENSIOLABS_ENABLE_NEW_DIRECTORY_STRUCTURE=true \
    --link sample_db:db \
    webridge/composer install --prefer-dist
    
docker run -d \
    -v $(pwd):/var/app \
    --link sample_db:db \
    -p 8080:80 \
    webridge/symfony-app
```