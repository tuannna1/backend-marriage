## Run without docker

- Create file env

    ```bash
    cp .env.example .env
    ```

- Install package

    ```bash
    composer install
    ```

- Create key application

    ```bash
    php saya key
    ```

- Execute migration database

    ```bash
    php saya migrasi --gen
    ```

- Run in development server

    ```bash
    php saya coba
    ```

## Run with docker

- Create file env

    ```bash
    cp .env.example .env
    ```

- Change and customize env file

    ```text
    BASEURL=https://your.domain.or.ipaddress:8080/

    DB_DRIV=pgsql
    DB_HOST=db
    DB_PORT=5432
    DB_NAME=undangan
    DB_USER=root
    DB_PASS=12345678

    JWT_KEY=valueIsSecure
    ```

- Build and run image

    ```bash
    docker compose up --build -d
    ```

- Execute migration

    > **_NOTE:_** Wait until the database is ready.

    ```bash
    docker exec undangan-app php saya migrasi --gen
    ```

## Deployment on vercel

- Clone or download this repository

    ```bash
    git clone https://github.com/tuannna1/backend-marriage.git
    ```

- Install package

    ```bash
    composer install
    ```

- Create .env file

    ```bash
    cp .env.example .env
    ```

- Execute migration database

    ```bash
    php saya migrasi --gen
    ```

- Create key application

    ```bash
    php saya key
    ```

- Push on your github.
- Create new project in vercel.
- Import from your repository.
- Change environment variables in your project on vercel.
- Add this :
  - DB_HOST (your host cloud dbms)
  - DB_PASS (your password cloud dbms)
  - DB_USER (your username cloud dbms)
  - DB_NAME (your name of database cloud dbms)
  - DB_PORT (your port cloud dbms)
  - DB_DRIV (type cloud dbms [ex. mysql or pgsql])
  - JWT_KEY [ex. 123]
  - HTTPS [true]
  - DEBUG [false]
  - LOG [false]
  - APP_KEY [copy from your local env]
- Click deployments tab in vercel project.
- Click the most recent deploy.
- Click dot three and redeploy.
- Done.

## Get Started Project

- Create a project with composer

    ```bash
    composer create-project kamu/kamu coba-app
    ```

- Move the folder

    ```bash
    cd coba-app
    ```

- Run in development server

    ```bash
    php saya coba
    ```
