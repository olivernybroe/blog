---
layout: post
title: PHP Insights v1.13.0 release
---

Thanks to [@50bhan](https://twitter.com/50bhan), [@jibbarth](https://twitter.com/jibbarth), [@bastien-phi](https://github.com/bastien-phi) and myself for the amazing work on release v1.13 of [PHP Insights](https://phpinsights.com)!

## GitHub action output support
In this new version a new formatter has been added for rendering the results to a GitHub action supported output. This means if you run PHP Insights with GitHub actions, you can now use the parameter `--format=github-action` and all of the insights will be displayed inline. 

![Screenshot of GitHub Action formatter](https://user-images.githubusercontent.com/3168281/72681882-2b25f700-3ac8-11ea-9950-579639b55c0f.png)

An example of the output and how to set it up can be found [here](https://github.com/Jibbarth/sandbox/pull/1/files#diff-1ce0ba77b4a9581558f919b927d75c31R1).

Thanks [@jibbarth](https://twitter.com/jibbarth), for this contribution!

## Sorting issues



## Custom formatters

## Multiple formatters

## Improved JSON output

## More reliable results

- Checking PHP version in composer
- Don't crash on empty namespace


This project is powered by the community, so feel free to contribute as there always are ways to help out.

