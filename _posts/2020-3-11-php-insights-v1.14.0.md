---
layout: post
title: PHP Insights v1.14.0 release
image: https://raw.githubusercontent.com/nunomaduro/phpinsights/master/art/logo.gif
image_square: https://github.com/nunomaduro/phpinsights/blob/master/art/heart.png?raw=true
tweet: https://twitter.com/OliverNybroe/status/1237709881542692864
---

Thanks to [@50bhan](https://twitter.com/50bhan), [devyk](https://github.com/devyk), [@Bastien_Phi](https://twitter.com/Bastien_Phi), [@jibbarth](https://twitter.com/jibbarth) and [@enunomaduro](https://twitter.com/enunomaduro) for the amazing work on release v1.13 of [PHP Insights](https://phpinsights.com)!

## Laravel 7 support
There is now support for Laravel 7!
However using Laravel 7 with PHP Insights requires PHP 7.3+ and PHPUnit 9.0+.  

If installation is failing, then upgrade phpunit with
```bash
composer require --dev phpunit/phpunit:^9.0 --update-with-dependencies
```

and then you can install/update PHP Insights.

Thanks [@Bastien_Phi](https://twitter.com/Bastien_Phi), for this contribution and [@jibbarth](https://twitter.com/jibbarth) for testing it out!


## Better Laravel support
PHP Insights now also reports usage of `ddd` and `tinker` helpers, as they shouldn't be in the production code.  
When using closures with Laravel, it will not report it as an error anymore, to not use static closures.  

Thanks [@enunomaduro](https://twitter.com/enunomaduro) and [@OliverNybroe](https://twitter.com/OliverNybroe) for this contribution!

## Setting min requirements in configuration file
It is now possible to define the min requirements for each metric directly in the config file, instead of as commandline arguments.  
This can be done by adding the following to your configuration file
```php
'requirements' => [
     'min-quality' => 0,
     'min-complexity' => 0,
     'min-architecture' => 0,
     'min-style' => 0,
     'disable-security-check' => false,
]
```

Thanks [devyk](https://github.com/devyk) for this contribution!

## Aggregate diffs in the same error
We now aggregates diffs of the same file in the same error!
Previous, we were advising users to remove code ( that was added on the omitted issues ).
![screenshot showing aggregation](https://user-images.githubusercontent.com/5457236/76355594-ddce4500-6314-11ea-98df-01c63c320601.png)

Thanks [@enunomaduro](https://twitter.com/enunomaduro) for this contribution!

## Fixed bugs when running on invalid PHP code
Some invalid PHP code caused PHP Insights to crash or being stuck in an infinite loop.  

Big thanks to [@50bhan](https://twitter.com/50bhan) for finding the issues and viable long term solution to this problem!


This project is powered by the community, so feel free to contribute as there always are ways to help out.
We can be found on GitHub at [nunomaduro/phpinsights](https://github.com/nunomaduro/phpinsights) and remember to follow us on twitter ([@phpinsights](https://twitter.com/phpinsights))!
