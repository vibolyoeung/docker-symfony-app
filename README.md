PHP5 with PostgreSQL driver and PHPUnit
=====

Basic Usage
------

```
docker run -v $(pwd):/app webridge/phpunit
```

Link to a Database
------

```
docker run --name db_name -d postgresql

docker run \
    -v $(pwd):/app \
    --link db_name:db \
    webridge/phpunit
```

You may add `PHPUnit` parameters such as `-c app/` at the end:

```
docker run \
    -v $(pwd):/app \
    --link db_name:db \
    webridge/phpunit -c app/
```