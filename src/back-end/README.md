# Back-end

The backend is built on top of [NodeJS](https://nodejs.org/es/), using [expressJS](https://expressjs.com/) and other cool tools like [Sequelize](https://sequelize.org/) and [Docker](https://www.docker.com/).

## Requeriments

- node >= 14
- Docker engine 1.13.0+ *(only if you want to use docker, this is optional)*
- Postgres SQL >= 9.6

## Setup 

First clone the repository

```bash
git clone https://github.com/itsalb3rt/ta-vivo-api
```

Now install all the dependencies

```bash
yarn
```

Now you need the environmente file, make a copy of the `.env.example` file

```bash
cp .env.example .env
```

This environment file contains the variables and values necessary to start the front-end without any further complications.

Now you can run the API

```bash
yarn dev
```

## Setup with Docker

First clone the repository

```bash
git clone https://github.com/itsalb3rt/ta-vivo-api
```

Now install all the dependencies

```bash
yarn
```

Now you need the environmente file, make a copy of the `.env.example` file

```bash
cp .env.example .env
```

💡 Tip: If you want connect to database container, set the env var `DATABASE_HOST=host.docker.internal`

now you can run docker-compose

```bash
docker-compose -f docker-compose.dev.yml up -d
```

## Environment variables

### Required

The list below is the required environment variables to run the API.

**PORT**: The port to expose the API.

**ENVIRONMENT**: This can be `development` or `test` or `production` depend of the environment. for example in `development` mode, the mail server is disabled.

---

Database

```
DATABASE_HOST
DATABASE_PORT
DATABASE_NAME
DATABASE_USER
DATABASE_PASSWORD
```

Admin user

```bash
ADMIN_USERNAME # This is a EMAIL, use a fake email if you want
ADMIN_PASSWORD
```

**TOKEN_KEY**: Your JWT secret, generate some strong random key.

---

### non-required

**DOMAIN**: If you use traefik as proxy, you can specify some custom domain.

**FORCE_SYNC**: This is a destructive variable, if this set in `true` all the tables in the database with some name like any model in the API are dropped.

## Notification variables

**TELEGRAM_BOT_TOKEN**: A telegram bot token to receive notifications via telegram.

---

All the variables below are required if you want to use Slack. Follow the documentation [https://slack.dev/bolt-js/concepts](https://slack.dev/bolt-js/concepts)

<img :src="$withBase('/img/slack-integration.png')" />

```
SLACK_CLIENT_ID
SLACK_CLIENT_SECRET
SLACK_REDIRECT_URI
SLACK_SIGNING_SECRET
SLACK_BOT_TOKEN
SLACK_BOT_PORT
```
---

All the variables below are required if you want to use discord. Follow the documentation [https://discordjs.guide/preparations/setting-up-a-bot-application.html#creating-your-bot](https://discordjs.guide/preparations/setting-up-a-bot-application.html#creating-your-bot)

<img :src="$withBase('/img/discord-integration.png')" />

```
DISCORD_CLIENT_ID
DISCORD_CLIENT_SECRET
DISCORD_REDIRECT_URI
```

---

All the next variables is required if you want receive notification via email.

```
MAIL_HOST
MAIL_PORT
MAIL_EMAIL
MAIL_PASSWORD
```
---

Payment with Paypal

```
PAYPAL_API
PAYPAL_CLIENT_ID
PAYPAL_APP_SECRET
PAYPAL_PRO_SUBSCRIPTION_ID
PAYPAL_ENTERPRISE_SUBSCRIPTION_ID
PAYPAL_ENTERPRISEPLUS_SUBSCRIPTION_ID
```