---
layout: post
title: Using WingLang for Advent of Code 2023
image: https://raw.githubusercontent.com/olivernybroe/olivernybroe.github.io/master/images/mitmproxy-android.webp
image_square: https://raw.githubusercontent.com/olivernybroe/olivernybroe.github.io/master/images/mitmproxy-android.webp
tweet:
---

I have recently been using a new language called Wing and I chose to use it for the Advent of Code 2023.  
If you are not familiar with WingLang, it is a new language designed for the cloud. It combines infrastructure and 
runtime in a single language, and it has a local simulator for quick feedback loop on your cloud resources.
I highly recommend checking it out at [winglang.io](https://winglang.io).

The reason why I did this was because doing AoC is a great way to learn a new language and find out what
features you find missing or what you like about the language.  
I also journaled my experience of this in Wing's Slack and had other people join in on the fun. This is one of my 
favorite things about Wing, the community is very supportive and generally just good vibes.

In this article I'll break down my experience day by day and do a summary at the end.

## Day 1
![wing-aoc-day-1](/images/wing-aoc-day-1.png)

I started up on a new machine and installed WingLang. I had installed Wing before, so I already knew that
the process is straight forward with a simple `npm install -g winglang`.

I started on problem one which was about finding the first and last number in a string. The number could
both be identified with a digit or spelled out with letters.

One unique thing about Wing (except for the whole concept) is it has a built in `test` keyword, so I wanted to try that 
out.  
When writing my tests I kept missing an expectation API like `expect.equals`, so I instead wrote all my test assertions
with the `assert` function.  

As Wing is a cloud language they have added keywords called `inflight` and `preflight`, essentially meaning if the code
runs in runtime or compile/deployment time. This feature is very cool, but sadly for AoC I couldn't really find a 
use for it and used `inflight` for all my functions.

Wing is a null safe language, and have a syntax I have not used before in other languages for checking if a variable is 
null. Essentially it is checked with an `if let` statement, which means if the variable is not null, then run the code
and assign the variable to a new non-nullable variable.
    
```wing
let var someting: num? = nil;

if let definitySomething = something {
    // definitySomething will be of type `num` and if statement will run
}
```

The source code for day 1 can be found [here](https://github.com/olivernybroe/AdventOfCode2023/blob/master/day1/main.w).

## Day 2
![wing-aoc-day-2](/images/wing-aoc-day-2.png)

For day 2, when starting on the problem I saw that I had a great use case for classes this time, which gave me a chance
to explore the class syntax in Wing. I had to look up quite a lot in the language documentation, as there was a lot
of syntax in it that wasn't familiar to me or what was possible.  
This is a list of some of the things I had to look up:
- Class constructor is called `new`.
- Classes has to be defined as inflight or preflight, not instances.
- No default property value.
- Private by default for both methods and properties (not constructor).
- Static methods have toe define if inflight or preflight.

They were still quite enjoyable as I in general have a preference for doing OOP design. The points above is not things
I think should necessarily be changed, but it was just things I had to look up and get used to.

After day 2, I was made aware that Wing has an expectation API which I started to miss even more on day 2, as I wrote a
lot of tests for the problem.

The source code for day 2 can be found [here](https://github.com/olivernybroe/AdventOfCode2023/blob/master/day2/main.w).

## Day 3
![wing-aoc-day-3](/images/wing-aoc-day-3.png)

For this day I finally got to use the `expect` API, which gave me exactly that experience I wanted when writing my tests 
and looking at failing assertions.  
I did have one bigger issues with them and that was when running tests via the Web Console, the output was not rendered
correctly in the browser terminal, only looked correct in the actual terminal.  
This day was also the first day I encountered a bug in the language, when I was using the `copyMut` method on a mutable
array in inflight, it would crash when actually running the code. I had to change the code to convert the mutable array
to a non-mutable array and then back to a mutable array, which was a bit annoying.

The source code for day 3 can be found [here](https://github.com/olivernybroe/AdventOfCode2023/blob/master/day3/main.w).

## Day 4
![wing-aoc-day-4](/images/wing-aoc-day-4.png)

This day had a lot of data manipulation and I really felt the struggle of using a language still in early development.  
While I was thinking about how to solve the problem, one of my solutions required changing the increment of the for loop
however this turned out to not be supported by the language yet. I kept hitting problems like these with things I am 
used to existing in other languages around manipulating arrays of data or strings. On strings, I was missing a classic
chunking method and spend embarrassingly long time realising that the `substring` method second argument is an index and
not a length.  

One thing I realised is I really prefer doing chain method calls, however it was not that obvious when a method was 
chainable or when you had to wrap your data in a function instead. For example converting a string to a number is done
with `num.fromstr`, whereas I would prefer being able to do `"123".toNum()`. This might seem trivial, but it's very 
important that a language is consistent on if you can chain methods or not.

The source code for day 4 can be found [here](https://github.com/olivernybroe/AdventOfCode2023/blob/master/day4/main.w)

## Day 5
![wing-aoc-day-5](/images/wing-aoc-day-5.png)

This day I tried working a bit differently, I choose to use the `wing test` method primarily instead of running tests 
from the browser console. This change of workflow meant that assertion output was always rendered nicely, however it did
make me realise that the `log` function output is not rendered in the terminal, which is a bit annoying.  
In this task itself, the data that had to be manipulated was multiline, which showed me a problem that Wing has no way
of defining multiline strings. I had to replace newlines with `\n` instead. When doing multiline strings the compiler 
did not complain, it would instead crash at runtime.

As AoC is very data processing heavy I again felt the struggle of classic collection methods like a `map` or `filter`. 
I had a scenario which I wanted to solve with a generator, e.g. `yield` or lazy collections, however Wing does not have
this feature yet either.

The source code for day 5 can be found [here](https://github.com/olivernybroe/AdventOfCode2023/blob/master/day5/main.w)

## Conclusion

I unfortunately didn't get to finish the Advent of Code, and only got to day 5. I had a great time trying to solve the
tasks using WingLang, and I learned a lot about the language and what it can do.  
A lot of what makes Wing great is lost when doing AoC, as it is a cloud language and AoC is not about cloud. For example
one of my favorite Wing features is the visual graph emulation of your cloud resources, however for AoC I choose to just
create a cloud function which made my graph a bit boring to look at.  
I also never deployed any of my code, and only used the local simulator, this project never experienced the joy of 
easily deploying to the cloud.  

Wing actually support importing JavaScript code, so many of my issues could have been solved by using JavaScript and 
importing it into Wing. However, I choose to not do this, as I wanted to experience the language alone only and not just
do JavaScript for AoC.

Throughout this journey I stumbled upon a lot of bugs and missing features, however I am very happy with the language
still. I think it has a lot of potential, and I am looking forward to see how it will evolve in the future. The Wing 
team is very active and have already taken care of multiple of the bugs and features I found missing which shows their 
dedication to their community and language.


I hope you enjoyed this article and that you will check out WingLang at [winglang.io](https://winglang.io)!