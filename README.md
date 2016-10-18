# Sentry On-Premise

Official bootstrap for running your own [Sentry](https://sentry.io/) with [Docker](https://www.docker.com/).

## Requirements

 * Docker 1.10.0+
 * Compose 1.6.0+ _(optional)_

## Resources

 * [Documentation](https://docs.sentry.io/server/installation/docker/)
 * [Bug Tracker](https://github.com/getsentry/onpremise)
 * [Forums](https://forum.sentry.io/c/on-premise)
 * [IRC](irc://chat.freenode.net/sentry) (chat.freenode.net, #sentry)



 安装步骤：
 官网省略了docker-compse的使用方法，实际上使用compese是最方便最傻瓜话安装的。
 请在服务器最好预留足够的内存，一开始遇到了很奇怪的错误["ERROR: relation "sentry_option" does not exist at character 114"](https://github.com/getsentry/sentry/issues/3635)
- 在ubuntu server上安装docker和docker-compose工具，请自行google。

## Up and Running

Assuming you've just cloned this repository, the following steps 
will get you up and running in no time!

1. `mkdir -p data/{sentry,postgres}` - Make our local database and sentry config directories.
    This directory is bind-mounted with postgres so you don't lose state!
2. `docker-compose run --rm web config generate-secret-key` - Generate a secret key.
    Add it to `docker-compose.yml` in `base` as `SENTRY_SECRET_KEY`.
3. `docker-compose run --rm web upgrade` - Build the database.
    Use the interactive prompts to create a user account.
4. `docker-compose up -d` - Lift all services (detached/background mode).
5. Access your instance at `localhost:9000`!



 * [use docker-compose](https://github.com/getsentry/onpremise/pull/12/files)
