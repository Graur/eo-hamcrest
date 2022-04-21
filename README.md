<img src="https://www.yegor256.com/images/books/elegant-objects/cactus.svg" height="100px" />

[![EO principles respected here](https://www.elegantobjects.org/badge.svg)](https://www.elegantobjects.org)
<!-- [![DevOps By Rultor.com](http://www.rultor.com/b/Graur/eo-tests)](http://www.rultor.com/p/yGraur/eo-tests) -->
[![We recommend IntelliJ IDEA](https://www.elegantobjects.org/intellij-idea.svg)](https://www.jetbrains.com/idea/)

<!-- [![mvn](https://github.com/Graur/eo-tests/actions/workflows/mvn.yml/badge.svg?branch=master)](https://github.com/yegor256/eo-files/actions/workflows/mvn.yml) -->
<!-- [![PDD status](http://www.0pdd.com/svg?name=Graur/eo-tests)](http://www.0pdd.com/p?name=yegor256/eo-files) -->
[![codecov](https://codecov.io/gh/cqfn/eo/branch/master/graph/badge.svg)](https://codecov.io/gh/cqfn/eo)
<!-- [![Maven Central](https://img.shields.io/maven-central/v/org.eolang/eo-files.svg)](https://maven-badges.herokuapp.com/maven-central/org.eolang/eo-files) -->

[![Hits-of-Code](https://hitsofcode.com/github/Graur/eo-tests)](https://hitsofcode.com/view/github/Graur/eo-tests)
![Lines of code](https://img.shields.io/tokei/lines/github/Graur/eo-tests)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/Graur/eo-tests/blob/main/LICENSE.txt)

[EOLANG](https://www.eolang.org) objects for testing.

This is how you can write your own tests in EO:

```
+package org.eolang
+alias org.eolang.test.assert-equals

[] > arithmetic-add-works
  assert-equals > @
    "two numbers"
    5.add 1
    6
```

Some assertions object for testing:

1) Equals:
```
+package org.eolang
+alias org.eolang.test.assert-equals

[] > arithmetic-add-works
  assert-equals > @
    "two numbers"
    5.add 1
    6
```

output message will be: 
```PASSED``` 
and return: ```TRUE```

2) Not equals:
```
+package org.eolang
+alias org.eolang.test.assert-not-equals

[] > arithmetic-add-works
  assert-not-equals > @
    "two numbers"
    5.add 1
    6
```

output message will be: 
```
expected: <6> not equal to: <6>
```
and return: ```FALSE```

3) Greater than:
```
+package org.eolang
+alias org.eolang.test.assert-gt

[] > b
  assert-gt > @
    "one number greater than another one"
    5.add 6
    8
```

output message will be:
```PASSED```
and return: ```TRUE```

4) Less than:
```
+package org.eolang
+alias org.eolang.test.assert-lt

[] > b
  assert-lt > @
    "one number less than another one"
    5.add 6
    8
```

output message will be:
```expected: <11> less than: <8>```
and return: ```FALSE```

5) True:
```
+package org.eolang
+alias org.eolang.test.assert-true

[] > b
  assert-true > @
    "number is equal to another number"
    5.eq 5
```

output message will be:
```PASSED```
and return: ```TRUE```

6) False:
```
+package org.eolang
+alias org.eolang.test.assert-false

[] > b
  assert-false > @
    "number is not equal to another number"
    5.eq 5
```

output message will be:
```expected: <5.eq 5> is false```
and return: ```FALSE```

## How to Contribute

Fork repository, make changes, send us a pull request.
We will review your changes and apply them to the `master` branch shortly,
provided they don't violate our quality standards. To avoid frustration,
before sending us your pull request please run full Maven build:

```bash
$ mvn clean install -Pqulice
```

You will need Maven 3.3+ and Java 8+.
