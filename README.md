phpnats
=======

**Travis**

* Master: [![Build Status](https://travis-ci.org/repejota/phpnats.png?branch=master)](https://travis-ci.org/repejota/phpnats)
* Develop: [![Build Status](https://travis-ci.org/repejota/phpnats.png?branch=develop)](https://travis-ci.org/repejota/phpnats)

**Insight**

* [![SensioLabsInsight](https://insight.sensiolabs.com/projects/3fb84121-278d-489f-8394-d95c3e3b05d2/mini.png)](https://insight.sensiolabs.com/projects/3fb84121-278d-489f-8394-d95c3e3b05d2)


A PHP client for the [NATS messaging system](https://nats.io).

>  Note: phpnats is under heavy development.

Requirements
------------

* php ~5.4
* [nats](https://github.com/derekcollison/nats) or [gnatsd](https://github.com/apcera/gnatsd)


Usage
-----

### Basic Usage

```php
$client = new \Nats\Connection(verbose=True);
$client->connect();

# Simple Publisher
$client->publish("foo", "foo bar");

# Simple Subscriber
$callback = function($payload)
{
    printf("Data: %s\r\n", $payload);
};
$client->subscribe("foo", $callback);

# Wait for 1 message
$client->wait(1);
```


Tests
-----

Tests are in the `tests` folder.
To run them, you need `PHPUnit` and execute `make test`.


## Creators
-----------

**Raül Pérez**

- <https://twitter.com/repejota>
- <https://github.com/repejota>

**Adrià Cidre**

- <https://twitter.com/adriacidre>
- <https://github.com/adriacidre>


License
-------

MIT, see [LICENSE](LICENSE)
