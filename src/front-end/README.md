# Front-end

The front-end is basically done in [vue](https://vuejs.org/guide/introduction.html), and a wonderful framework called [Quasar](https://quasar.dev/) is used.

## Setup

First clone the repository

```bash
git clone https://github.com/ta-vivo/ta-vivo
```

Now install all the dependencies

```bash
yarn
```

Now you need the environmente file, make a copy of the `.env.example` file

```bash
cp .env.example .env
```

Check the [Environment variables](#environment-variables) before running the project to set the correct values.

Now you can run the app

```bash
quasar dev
```
## Environment variables

### Required
**API**: The application API URL

**VUE_APP_NAME**: The name render in the page title or page content like terms and conditions etc.

To get supabase URL and key, you need to create a supabase account and create a new project. Then you can get the URL and key from the project settings. [https://supabase.com/docs/guides/with-vue-3#get-the-api-keys](https://supabase.com/docs/guides/with-vue-3#get-the-api-keys)

**SUPABASE_PROJECT_URL**: The supabase project url
**SUPABASE_ANON_PUBLIC_KEY**: The supabase anon public key

### Non-required
**VUE_APP_URL**: This value is a URL to use in legal page like terms and conditions, policy privacy.

**VUE_APP_CONTACT_EMAIL**: The email to show in legal pages.

**PAYPAL_CLIENT_ID**: This is unique to each instance, for example, if you like to self-host and put it as a service you need to create a PayPal business account and get your own PayPal client id.

## Authentication with social networks

All the documentation is on the official Supabase page, [https://supabase.com/docs/guides/auth](https://supabase.com/docs/guides/auth)

At this moment, only the list below is supported.

- Discord [https://supabase.com/docs/guides/auth/auth-discord](https://supabase.com/docs/guides/auth/auth-discord)
- Github [https://supabase.com/docs/guides/auth/auth-github](https://supabase.com/docs/guides/auth/auth-github)
- Google [https://supabase.com/docs/guides/auth/auth-google](https://supabase.com/docs/guides/auth/auth-google)
- Slack [https://supabase.com/docs/guides/auth/auth-slack](https://supabase.com/docs/guides/auth/auth-slack)

```
SUPABASE_PROJECT_URL
SUPABASE_ANON_PUBLIC_KEY
```