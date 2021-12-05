
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

3. Remove `.git` folder

```
rm -rf .git/
```

4. Create a new repository

```
git init

git remote add origin https://<TOKEN>@github.com/<USER_NAME>/<PROJECT_NAME>.git
```

5. Update `.env` file.

6. Build and run docker containers using docker-compose

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

2. Remove `.gitignore` file

```
rm .gitignore
```

3. Create a Symfony application with one of the following commands

```
# traditional web application
composer create-project symfony/website-skeleton .

# microservice, console application or API
composer create-project symfony/skeleton .
```

4. Check the website

```
localhost:8080
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
```

## License

Code released under the [MIT license](./LICENSE).
