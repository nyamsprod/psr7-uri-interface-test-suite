[WIP] PSR-7 UriInterface test suite
=======

Motivation
-------

While developing [League Url](https://github.com/thephpleague/url/) version 4, I wanted to:

- implement the [PSR-7 UriInterface](http://php-fig.org/psr-7/#3-5-psr-http-message-uriinterface);
- compare objects implementing this interface easily with a `Url::sameValueAs` method;

On the `League\Url` test suite the method worked because I mocked the interface but on real world implementation it failed miserably. So I setup this test suite to compare implementations against what the interface expects.

This is a work in progress. Feel free to update and improve the tests. It will help everyone get a real interoperable UriInterface.

Tested implementations
-------

Out of the box this package can run the tests against the following implementations (order alphabetically):

- [Guzzle PSR-7](https://github.com/guzzle/psr7)
- [League Url](https://github.com/thephpleague/url/) (version 4.x)
- [Slim](https://github.com/slimphp/Slim/tree/3.x)
- [Zend Diactoros](https://github.com/zendframework/zend-diactoros)

System Requirements
-------

You need:

- **PHP >= 5.5.0** or **HHVM >= 3.6**, but the latest stable version of PHP/HHVM is recommended
- the `mbstring` extension
- the `intl` extension

Install
-------

```
$ composer require nyamsprod/psr7-uriinterface-test-suite
```

Testing
-------

To run the tests, run the following command from the project folder.

``` bash
$ phpunit
```

Adding a new implementation
-------

- Make sure your implementation is available on packagist first
- Clone this repo
- Update the composer.json file with your package
- Add a new class in the `test` directory for your implementation that extends the `AbstractTestPsr7UriInterface` abstract class. You can copy/paste an implementation test suite to see how it works. Implements the `createUriObject` abstract method.
- run the TestSuite it should works!!
- you can submit your modification via Pull Request.


Contributing
-------

Contributions are welcome and will be fully credited. Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

Credits
-------

- [ignace nyamagana butera](https://github.com/nyamsprod)
- [All Contributors](https://github.com/nyamsprod/url/contributors)

License
-------

The MIT License (MIT). Please see [License File](LICENSE) for more information.