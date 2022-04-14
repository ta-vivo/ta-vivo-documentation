# Front-end

The front-end is basically done in [vue](https://vuejs.org/guide/introduction.html), and a wonderful framework called [Quasar](https://quasar.dev/) is used.

## Setup

First clone the repository

```bash
git clone https://github.com/itsalb3rt/ta-vivo
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

Now you can run the app

```bash
quasar dev
```
## Environment variables

### Required
**API**: The application API URL

**VUE_APP_NAME**: The name render in the page title or page content like terms and conditions etc.

### Non-required
**VUE_APP_URL**: This value is a URL to use in legal page like terms and conditions, policy privacy.

**VUE_APP_CONTACT_EMAIL**: The email to show in legal pages.

**PAYPAL_CLIENT_ID**: This is unique to each instance, for example, if you like to self-host and put it as a service you need to create a PayPal business account and get your own PayPal client id.