# Introduction to Automated Testing in R

---

## What is testing?

* Everyone probably does it already, runs a function with some input and looks at the output to ensure that it matches expected
   1. Write code
   1. Run code
   1. Check some output against what you expect
   1. Repeat
* Testing formalises this process and provides an easy way to run and re-run tests

---

## Why test?

* Ensures code produces what you expect it to
* Allow safe refactoring and extending
* Catches regressions
* Confidence to make changes

---

## Why test?

* Encouraging breaking code into manageable testable units instead of monolithic code

---

## When to test

Software developers will tell you to do it always for all code (except maybe prototype code)

In any code which will be 
* Used by others
* You will extend and revisit in the future
* And the code is testable

---

## How to test

---

## Setup

One time setup for a package

```
usethis::use_testthat()
```
Will create a `tests/testthat` directory with a script `tests/testthat.R`

---

## Create a new test

```
usethis::use_test("my-test")
```

Or create a file in `tests/testthat/` directory called `test-*.R`

---

## Anatomy of a test

* **context** - human readable name for a test file
* **tests** - the tests themselves, with a description and test code including expectations
* **expectation** - describe the expected result of a computation, can be things such as equality, class type, does it throw an error

```
context("sqrt")

testthat::test_that("sqrt works as expected", {
  expect_equal(sqrt(36), 6)
})
```

---

## Running tests

* Tests for a package 
```
testthat::test_package()``` 
Ctrl+Shift+T in RStudio or Build -> Test Package
* As part of 
```
R CMD check
``` 
Ctrl+Shift+E in RStudio or Build -> Check Package

---

## Running tests

* Test a single file 
```
testthat::test_file("path/to/file")
```
   * Can get this on a shortcut too using RStudio Addins see Tools -> Addins -> Keyboard Shortcuts

---

## Running tests outside of a package

* Not as convenient as running as part of a package workflow
* Create functions in an R file
* `source` the R file in the test script or manually before running the tests
* Call using 
```
testthat::test_file("path/to/file")
```
or 
```
testthat::test_dir("path/to/dir")
```

---

## Continuous integration with travis

---

## Travis CI

* Continuous integration - automating the building and testing of code on commit to github
* Automates checking of your package
* Builds on a "clean" machine giving confidence that your code will work for others
* Can use it to generate coverage reports and other fancy metrics

---

## Travis setup

One time setup
```
usethis::use_travis()
```

Follow the instructions to turn on travis for your github repo and add the badge to your `README.md`

Travis will then automatically run tests on every git commit

---

## Links and other cool stuff

* [testthat](https://testthat.r-lib.org/)
* [R packages testing chapter](http://r-pkgs.had.co.nz/tests.html)
* [covr](https://github.com/r-lib/covr)
* [Travis R](https://docs.travis-ci.com/user/languages/r/)
* [Julia Silge Travis begginers guide](https://juliasilge.com/blog/beginners-guide-to-travis/)
* [Mockery](https://github.com/r-lib/mockery)
* [List of expect_ functions](https://testthat.r-lib.org/reference/index.html)

