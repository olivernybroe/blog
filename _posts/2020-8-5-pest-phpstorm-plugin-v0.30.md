---
layout: post
title: Pest PhpStorm plugin v0.3.0 release
image: https://github.com/pestphp/art/blob/master/logo.gif?raw=true
image_square: https://raw.githubusercontent.com/pestphp/pest-intellij/c1dfc299bad12f3a43e23a979804611cb108885b/src/main/resources/logo.svg
tweet: 
---

Thanks to [@OliverNybroe](https://twitter.com/OliverNybroe), [@Adelf32](https://twitter.com/Adelf32) for the amazing work on release v0.3.0 of [Pest-intellij](https://pestphp.com/)!


This blogpost will contain all features in the plugin as this is the first official release.  
The installation instructions can be found [here](https://github.com/pestphp/pest-intellij#installation).


## Running test
It is now possible to run pest test in phpstorm like any other test, by simply selecting the runner with the pest icon.
![Run test](https://i.imgur.com/0TJibsE.png)
After pressing run the results is in the Run window.
![Run window](https://i.imgur.com/HRt9Xzq.png)

### With inline actions
A test can also be executed on a specific line by pressing the marker on that line.
![line-marker](https://i.imgur.com/z74xesd.png)
It is also possible to execute a test on a specific line by opening the run configuration while having the cursor on that line.
![Run Configuration](https://i.imgur.com/3z9ivww.png)

### With debugger
For all the debugger users out there, it is also possible to run the tests with the debugger.  
Simply press the run with debug icon, and the tests will run with the debugger enabled.
![debugger](https://i.imgur.com/3DabCAy.png)

This should work with xdebug and zend debugger, however only xdebug has been tested.

### With coverage
Getting code coverage is also straight forward.  
Use the button for running with code coverage, and the results will be shown in phpstorm.
![coverage-running](https://i.imgur.com/NvSLx3w.png)

![coverage-results](https://i.imgur.com/1qLN3hZ.png)

## Autocompletion
This plugin does not only add support for running tests, autocompletion is also added thanks to [@Adelf32](https://twitter.com/Adelf32).

### On PhpUnit testcase methods
Autocompletion for PhpUnit test case methods are also possible.  
By declaring that the test `uses` a class, autocompletion for that class can be done.  
In the screenshot below the `uses` class is the default Laravel testcase class, and therefore autocompletion for the `assertAuthenticated` method is possible.
![uses-autocompletion](https://i.imgur.com/abG18wx.png)

### On fields declared in `beforeEach` and `afterEach`
Declaring a field in `beforeEach` and `afterEach` can be autocompleted in the test.
![declared-field](https://i.imgur.com/vxM3Tjt.png)


This project is powered by the community, so feel free to contribute as there always are ways to help out.
We can be found on GitHub at [pestphp/pest-intellij](https://github.com/pestphp/pest-intellij).

