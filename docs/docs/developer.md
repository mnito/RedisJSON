---
title: "Developer notes"
linkTitle: "Developer notes"
weight: 7
description: >
    Notes on debugging, testing and documentation
---

## Debugging

Compile after settting the environment variable `DEBUG`, e.g. `export DEBUG=1`, to include the
debugging information.

## Testing

Python is required for RedisJSON's module test. Install it with `apt-get install python`. You'll also
need to have [redis-py](https://github.com/redis/redis-py) installed. The easiest way to get
it is using pip and running `pip install redis`.

The module's test can be run against an "embedded" disposable Redis instance, or against an instance
you provide to it. The "embedded" mode requires having the `redis-server` executable in your `PATH`.
To run the tests, run the following in the project's directory:

```bash
$ # use a disposable Redis instance for testing the module
$ make test
```

You can override the spawning of the embedded server by specifying a Redis port via the `REDIS_PORT`
environment variable, e.g.:

```bash
$ # use an existing local Redis instance for testing the module
$ REDIS_PORT=6379 make test
```
