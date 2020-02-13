---
layout: post
title: PHP Insights v1.13.0 release
image: https://raw.githubusercontent.com/nunomaduro/phpinsights/master/art/logo.gif
image_square: https://github.com/nunomaduro/phpinsights/blob/master/art/heart.png?raw=true
tweet: https://twitter.com/OliverNybroe/status/1227941277578211329
---

Thanks to [@50bhan](https://twitter.com/50bhan), [@jibbarth](https://twitter.com/jibbarth), [@Bastien_Phi](https://twitter.com/Bastien_Phi) for the amazing work on release v1.13 of [PHP Insights](https://phpinsights.com)!

## GitHub action output support
In this new version a new formatter has been added for rendering the results to a GitHub action supported output. This means if you run PHP Insights with GitHub actions, you can now use the parameter `--format=github-action` and all of the insights will be displayed inline. 

![Screenshot of GitHub Action formatter](https://user-images.githubusercontent.com/3168281/72681882-2b25f700-3ac8-11ea-9950-579639b55c0f.png)

An example of the output and how to set it up can be found [here](https://github.com/Jibbarth/sandbox/pull/1/files#diff-1ce0ba77b4a9581558f919b927d75c31R1).

Thanks [@jibbarth](https://twitter.com/jibbarth), for this contribution!

## Sorting issues
Issues are now sorted, which means it is now much easier to fix all issues, as they are grouped by the file in each insight.

![Sorted images screenshot](https://i.imgur.com/xPHSjoI.png)

Thanks [@Bastien_Phi](https://twitter.com/Bastien_Phi), for this contribution!

## Custom output
It is now possible to define a custom output, simply supply a class which implements [`Formatter`](https://github.com/nunomaduro/phpinsights/blob/master/src/Application/Console/Contracts/Formatter.php) and PHP Insights will be using that one.

```bash
phpinsights analyse --format=\\MyNamespace\\Class
```

## Multiple formats in output
The tool now also supports specifying mulitple formatters, simply add multiple `--format` args.

```bash
phpinsights analyse --format=json --format=github-action
```

## Improved JSON output
The JSON output now also contains an attribute called `diff`, which contains the diff for the specified code. A schema file is [available](https://github.com/nunomaduro/phpinsights/blob/master/schema.json) to see the full JSON output format.

## More reliable results
Some improvements were made, so PHP Insights gives better results.

### Don't crash on empty namespace
A bug was fixed, which caused PHP Insights when a namespace was added without a name on the namespace.

Thanks [@50bhan](https://twitter.com/50bhan) for fixing this!

### Checking PHP version in composer
As [v.1.12](https://nunomaduro.com/php-insights-v1-12-is-out) added support for Slevomat Coding Standard v6, some new insights  were added which supports native type hints from PHP 7.4. However many open source projects run php insights on multiple php version, which caused it to fail when testing on PHP 7.4, but not on any lower versions. This feature added support for checking the php version specified in `composer.json` and disable native type hint checking if PHP version is before 7.4.


This project is powered by the community, so feel free to contribute as there always are ways to help out.
We can be found on GitHub at [nunomaduro/phpinsights](https://github.com/nunomaduro/phpinsights).

