## Make any wordpress code run within Docker container

This makes it easy for developers to run any wordpress codebase in a docker container

### Prerequisites
To make use of this, you'll need
* [Docker Compose](https://docs.docker.com/compose/install/)
* a wordpress codebase
* wordpress database backup

### Preperation
* Stop any other servers running locally (as docker-compose is mapping to port 80)
* Place sql backup in `/sql` folder as file starting with 02_ i.e. `02_backup.sql`
* Place your wordpress code in `/wp` folder
* Set wp-config to use the following settings

```php
  define('DB_NAME', 'wordpress');
  define('DB_USER', 'root');
  define('DB_PASSWORD', '');
  define('DB_HOST', 'mysql');
```
* Run docker-compose

```
docker-compose up
```

* Give it few minutes to download images and init containers
* Open a browser and access [http://localhost](http://localhost)

### Thats it
You're done!
