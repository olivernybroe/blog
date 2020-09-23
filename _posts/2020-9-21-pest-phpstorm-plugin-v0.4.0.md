---
layout: post
title: Pest PhpStorm plugin v0.4.0 release
image: https://raw.githubusercontent.com/pestphp/pest-intellij/master/art/banner.png
image_square: https://github.com/olivernybroe/olivernybroe.github.io/blob/master/images/pest-logo-square.png?raw=true
tweet: https://twitter.com/OliverNybroe/status/1308657258558091266
---

Thanks to [@OliverNybroe](https://twitter.com/OliverNybroe), [@Adelf32](https://twitter.com/Adelf32) for the amazing work on release v0.4.0 of [Pest-intellij](https://pestphp.com/)!

This blogpost will contain a summary of the changes from v0.3.0 to v0.4.0

## Added navigation between test and subject
It is now possible ot navigate between a test and the test subject.  
Go to a test subject and press `Shift+Command+T` and it will navigate to the test files for this subject.

![test-navigation](/images/test-navigation.gif)

## Added dark/light mode icons
The plugin now has icons which works better when using dark mode in IntelliJ.  
So depending on if you prefer light themes or dark themes the icon will change according to the image below.
![dark-light-icons](/images/dark-light-mode-icons.png)


Thanks to [@Caneco](https://twitter.com/Caneco) for making the icons!

## Added inspection for duplicate test names
In Pest, it is not allowed to have the same test name twice in the same file.  
The plugin now has automatic validation for checking this, and will warn the user.

![duplicate-test-name](/images/duplicate-test-name.jpg)

## Added auto completion for fields declared in `beforeEach`
There are now autocompletion for fields declared in `beforeEach`!  
So if you bind a field to `$this` in your `beforeEach`, you can now access them
in your tests.

![before-properties](/images/beforeProperty.gif)

## Added auto completion for static PhpUnit methods
In PhpUnit there are a bunch of methods which are actually static methods or protected methods.  
Before this release, the plugin was not able to autocomplete them, however this works now.

![auto-completion](/images/static-autocompletion.gif)

## Added PCOV coverage engine support
In Pest when doing autocompletion, you could only use Xdebug before, however in this new version
PCOV is also support. By editing your run configuration you can select your preferred coverage engine.

![pcov-support](/images/pcov-support.png) 


### Bug fixes
The following list is a list of fixes which was released together with this version.

- Fixed duplicate test name error when no test name is given yet. ([#61](https://github.com/pestphp/pest-intellij/pull/61))
- Fixed finding tests with namespace at the top. ([#65](https://github.com/pestphp/pest-intellij/pull/65))
- Fixed allow location to be null in location provider. ([#68](https://github.com/pestphp/pest-intellij/pull/68))
- Fixed rerunning tests with namespaces ([#69](https://github.com/pestphp/pest-intellij/pull/69))

This project is powered by the community, so feel free to contribute as there always are ways to help out.
We can be found on GitHub at [pestphp/pest-intellij](https://github.com/pestphp/pest-intellij).
