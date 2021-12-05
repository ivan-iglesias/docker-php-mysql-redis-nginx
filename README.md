
# Docker PHP Template

Docker compose boilerplate to setup a PHP project with MySQL and Redis using Nginx as webserver.

## Usage

1. Clone the project

```
git clone https://github.com/ivan-iglesias/docker-php-mysql-redis-nginx.git <PROJECT_DIRECTORY>
```

2. Change current working directory

```
cd <PROJECT_DIRECTORY>
```

3. Set your project's origin

```
git remote set-url origin https://<TOKEN>@github.com/<USER_NAME>/<PROJECT_NAME>.git
```

4. Update `.env` file.

5. Build and run docker containers using docker-compose

```
docker-compose up -d --build
```

If you want to display log output from services.

```
docker-compose logs -f <SERVICE_NAME>
```

## Symfony project

1. Enter into php docker container

```
docker exec -it <APP_NAME>_php bash
```

2. Create a Symfony application with one of the following commands

```
composer create-project symfony/website-skeleton .

composer create-project symfony/skeleton .
```

## Xdebug with VCode

Edit `.vscode/launch.json` file setting port and pathMappings.

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Listen for Xdebug",
            "type": "php",
            "request": "launch",
            "port": 9003,
            "pathMappings": {
                "/var/www/<APP_NAME>/": "${workspaceFolder}/src"
            }
        },
        ...
```

## License

Code released under the [MIT license](./LICENSE).
