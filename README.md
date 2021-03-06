# sancus

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Software License][ico-license]](LICENSE.md)
[![Build Status][ico-travis]][link-travis]
[![Total Downloads][ico-downloads]][link-downloads]

[Binomial proportion confidence intervals](https://en.wikipedia.org/wiki/Binomial_proportion_confidence_interval). Supported methods are Agresti-Coull, Wald and Wilson Score.

## Install

Via Composer

``` bash
$ composer require ozdemirburak/sancus
```

## Usage

``` php
$interval = new OzdemirBurak\Sancus\Intervals\AgrestiCoullInterval($positive = 25, $negative = 25, $confidence = 0.95);
print_r($interval->getInterval()); // Array([0] => 0.36644514398812, [1] => 0.63355485601188)
echo $interval->getLowerBound(); // prints 0.36644514398812

$interval = new OzdemirBurak\Sancus\Intervals\WaldInterval(10, 50);
print_r($interval->getInterval()); // Array([0] => 0.072367856116984, [1] => 0.26096547721635)
echo $interval->getUpperBound(); // prints 0.26096547721635

$interval = new OzdemirBurak\Sancus\Intervals\WilsonInterval(75, 25, 0.90);
print_r($interval->getInterval()); // Array([0] => 0.67282656258608, [1] => 0.81400207671582)
echo $interval->getScore(); // WilsonInterval only, same as $interval->getLowerBound(), prints 0.67282656258608
```

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) and [CONDUCT](CONDUCT.md) for details.

## Credits

- [Burak Özdemir][link-author]
- [All Contributors][link-contributors]

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[ico-version]: https://img.shields.io/packagist/v/ozdemirburak/sancus.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-travis]: https://img.shields.io/travis/ozdemirburak/sancus/master.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/ozdemirburak/sancus.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/ozdemirburak/sancus
[link-travis]: https://travis-ci.org/ozdemirburak/sancus
[link-downloads]: https://packagist.org/packages/ozdemirburak/sancus
[link-author]: https://github.com/ozdemirburak
[link-contributors]: ../../contributors
