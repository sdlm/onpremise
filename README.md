# Sentry On-Premise

Official bootstrap for running your own [Sentry](https://sentry.io/) with [Docker](https://www.docker.com/).

## Requirements

 * Docker 18.02.0+
 * docker-compose 1.21.2+
 
## Up and Running

Assuming you've just cloned this repository, the following steps
will get you up and running in no time!

There may need to be modifications to the included `docker-compose.yml` file to accommodate your needs or your environment. These instructions are a guideline for what you should generally do.

1. `docker-compose run --rm base config generate-secret-key` - Generate a secret key.
    Add it to `docker-compose.yml` in `base` as `SENTRY_SECRET_KEY`.
2. `docker-compose run --rm base upgrade` - Build the database.
    Use the interactive prompts to create a user account.
3. `docker-compose up -d` - Lift all services (detached/background mode).
4. Access your instance at `localhost:80`!

Note that as long as you have your database bind-mounted, you should
be fine stopping and removing the containers without worry.

## Securing Sentry with SSL/TLS

If you'd like to protect your Sentry install with SSL/TLS, there are
fantastic SSL/TLS proxies like [HAProxy](http://www.haproxy.org/)
and [Nginx](http://nginx.org/).

## Resources

 * [Documentation](https://docs.sentry.io/server/installation/docker/)
 * [Bug Tracker](https://github.com/getsentry/onpremise)
 * [Forums](https://forum.sentry.io/c/on-premise)
 * [IRC](irc://chat.freenode.net/sentry) (chat.freenode.net, #sentry)
