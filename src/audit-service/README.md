# Audit service

The only task of this service is to save the data that is generated with the user's actions, for example, updating a "check", deleting an integration or when the user is sent a notification.

[Repository](https://github.com/ta-vivo/ta-vivo-audit-log)

## Requeriments

- Go >= 1.18
- Docker engine 1.13.0+ *(only if you want to use docker, this is optional)*
- Postgres SQL >= 9.6

## Setup 

First clone the repository

```bash
git clone https://github.com/ta-vivo/ta-vivo-audit-log
```

Now install all the dependencies

```bash
go get
go install
```

Now you need the environmente file, make a copy of the `.env.example` file

```bash
cp .env.example .env
```

This environment file contains the variables and values necessary to start the front-end without any further complications.

Now you can run the API

```bash
go run ./src/
```

## Setup with Docker

First clone the repository

```bash
git clone https://github.com/ta-vivo/ta-vivo-audit-log
```

Now you need the environmente file, make a copy of the `.env.example` file

```bash
cp .env.example .env
```

💡 Tip: If you want connect to database container, set the env var `DB_HOST=host.docker.internal`

now you can run docker-compose

```bash
docker-compose up -d
```

## Environment variables

### Required

**PORT**: The port to expose the API.

**JWT_SECRET**: The secret to check the sign of the JWT. The same of the [API](https://github.com/ta-vivo/ta-vivo-api) 

---

Database

```
DB_HOST=localhost
DB_PORT=5432
DB_NAME=logs
DB_USER=postgres
DB_PASSWORD=postgres
```

## Usage

The unique enpoint is `/logs`, you can use the following methods:

POST
```json
{
    "userId": 1,
    "action": "update",
    "metaData": {
        "property": "value"
    }
}
```

## Current saved logs

The next section describe the current logs that are saved in the database with the current structure.

### Checks

```json
// On update, on Disable, on Enable and on Delete
{
    "userId": 1,
    "action": "update || delete",
    "metaData": {
        "entity":"check",
        {"old": {}},
        {"edited": {}}
    }
}
```

### Integrations

```json
// On update, on Delete and when the user request a integration test notification
{
    "userId": 1,
    "action": "update || test || delete",
    "metaData": {
        "entity":"integration",
        {"old": {}},
        {"edited": {}}
    }
}
```

### Auth

```json
// On forgot password and on reset password
{
    "userId": 1,
    "action": "password_change || password_forgot",
    "metaData": {
        "entity":"user",
        {"old": {}},
        {"edited": {}}
    }
}
```
```