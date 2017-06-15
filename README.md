# Docker PHP Artisan

A minimal Docker image for Laravel Artisan CLI based on official PHP image

# What is Artisan?

Artisan is the command-line interface included with Laravel. It provides a number of helpful commands that can assist you while you build your application.

You can read more about Artisan in [Laravel official documentation](https://laravel.com/docs/5.4/artisan).

# Using

To view a list of all available Artisan commands, run the `zackyjack/php-artisan` image with `list` command:

```sh
docker run --rm --interactive --tty \
    --volume $PWD:/app \
    zackyjack/php-artisan list
```

Or just:

```sh
docker run --rm --interactive --tty \
    --volume $PWD:/app \
    zackyjack/php-artisan
```

To serve application with `serve` command, you need to specify host to `0.0.0.0`, so you can open it in your host browser:

```sh
docker run --rm --interactive --tty \
    --publish 80:8000
    --volume $PWD:/app \
    zackyjack/php-artisan serve --host 0.0.0.0
```

And don't change default `serve` port, if you need to change port,  just specify it in `--publish` flag. E.g. to change port to 8080:

```sh
docker run --rm --interactive --tty \
    --publish 8080:8000
    --volume $PWD:/app \
    zackyjack/php-artisan serve --host 0.0.0.0
```

By default, Artisan runs as root inside the container. This can lead to permission issues on your host filesystem. You can run Artisan as your local user:

```sh
docker run --rm --interactive --tty \
    --volume $PWD:/app \
    --user $(id -u):$(id -g) \
    zackyjack/php-artisan make:migration create_tasks_table
```
