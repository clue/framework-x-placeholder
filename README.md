# Framework X

[![CI status](https://github.com/clue-access/framework-x/workflows/CI/badge.svg)](https://github.com/clue-access/framework-x/actions)

Framework X – the simple and fast micro framework for building reactive web applications that run anywhere.

* [Quickstart](#quickstart)
* [Documentation](#documentation)
* [Install](#install)
* [License](#license)

## Quickstart

Once everything is installed, you can now use this example to get started with
a new `app.php` file:

```php
<?php

require __DIR__ . '/../vendor/autoload.php';

$loop = React\EventLoop\Factory::create();
$app = new FrameworkX\App($loop);

$app->get('/', function () {
    return new React\Http\Message\Response(
        200,
        [],
        "Hello wörld!\n"
    );
});

$app->get('/users/{name}', function (Psr\Http\Message\ServerRequestInterface $request) {
    return new React\Http\Message\Response(
        200,
        [],
        "Hello " . $request->getAttribute('name') . "!\n"
    );
});

$app->run();
$loop->run();
```

That's it already! The next step is now to serve this web application.
One of the nice properties of this project is that is works both behind
traditional web server setups as well as in a stand-alone environment.

For example, you can run the above example using PHP's built-in webserver for
testing purposes like this:

```bash
$ php -S 0.0.0.0:8080 app.php
```

You can now use your favorite webbrowser or command line tool to check your web
application responds as expected:

```bash
$ curl -v http://localhost:8080/
HTTP/1.1 200 OK
…

Hello wörld!
```

## Documentation

Hooked?
See [website](https://framework-x.clue.engineering/) for full documentation.

## Install

[![A clue·access project](https://raw.githubusercontent.com/clue-access/clue-access/main/clue-access.png)](https://github.com/clue-access/clue-access)

*This project is currently under active development,
you're looking at a temporary placeholder repository.*

Do you want early access to my unreleased projects?
You can either be patient and wait for general availability or
consider becoming a [sponsor on GitHub](https://github.com/sponsors/clue) for early access.

Do you sponsor me on GitHub? Thank you for supporting sustainable open-source, you're awesome!
The prototype is available here: [https://github.com/clue-access/framework-x](https://github.com/clue-access/framework-x).

Support open-source and join [**clue·access**](https://github.com/clue-access/clue-access) ❤️

## License

This project will be released under the permissive [MIT license](LICENSE).

> Did you know that I offer custom development services and issuing invoices for
  sponsorships of releases and for contributions? Contact me (@clue) for details.
