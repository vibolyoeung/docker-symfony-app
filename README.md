Symfony App with PSQL Driver
=====

Basic Usage
-----------

```
docker run -d -v $(pwd):/var/app \
    -p 8080:80 \
    webridge/phpunit
```

Linking a Database
------------------

```
docker run -d -v $(pwd):/var/app \
    --link your_db:db \
    -p 8080:80 \
    webridge/phpunit
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
    webridge/phpunit
```