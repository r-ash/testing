# Introduction to Automated Testing in R

---

## Overview

* Why test
* When to test
* How to test

Convince that testing is valuable making code easier to understand and extend and will save time in the long run

---

## Why test?

* Make sure your code works
* Everyone probably does it already, runs a function with some input and looks at the output to ensure that it matches expected
** Write code
** Run code
** Check some output against what you expect
** Repeat

---

## Why test?

* Works fine for a code base which is small and simple but as dependencies grow and functions interact with each other starts getting messy just doing difficutly testing
* Writing formal tests gives a strategy for handling regressions giving confidence that you can go and change code and not create unintended side effects that you don't know about
* Shown to reduce bugs in production code

---

## Why test?

* Encouraging breaking code into manageable testable units instead of monolithic code

---

## When to test

---

## When to test

* In any code which will be 
** Used by others
** You will extend and revisit in the future

Avoiding it on exploratory one time throw away code - prototyping etc.

---

## How to test

---

## Setup

* Setting up test
* Install and use this on a package

---

## Writing test

* context
* test
* expect that

---

## Running test

* testthat on a file
* testthat for a whole package
* Rstuido shortcuts
* as pacakge check

---

## Continuous integration with travis

---

## Travis CI

* Continuous integration
* Your passing tests aren't just a result of particular way you have your system setup

---

## Travis setup

* triggered on build


