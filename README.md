Hydiomatic
==========

[![Build Status](https://travis-ci.org/algernon/hydiomatic.png?branch=master)](https://travis-ci.org/algernon/hydiomatic)
[![Downloads](https://pypip.in/d/hydiomatic/badge.png)](https://crate.io/packages/hydiomatic)
[![Version](https://pypip.in/v/hydiomatic/badge.png)](https://crate.io/packages/hydiomatic)

Hydiomatic is a static code analyser for [Hy](http://hylang.org/),
that can analyse a form, and suggest a simplification, or a more
idiomatic alternative.

The software is under heavy development, and has serious limitations,
but it can already perform interesting transformations.

Installation
------------

Hydiomatic depends on [adderall][adderall], and can be installed the
usual way with `pip`:

```shell
$ pip install -r requirements.txt
```

 [adderall]: https://github.com/algernon/adderall

Usage
-----

The library can be used either via the `bin/hydiomatic.hy` script:

```shell
$ bin/hydiomatic.hy -d FILENAME
```

For more information on what the script can do, run `bin/hydiomatic.hy
--help`.

Or programmatically:

```clojure
(import [hydiomatic.core [*]])

(simplify '(if (not (= 0 (- 1 1))) 
             (do (print (+ 1 (+ 2 3)) [a b {"c" (+ a 1)}]))))
;=> (unless (is_zero (dec 1))
;     (print (+ 1 2 3) [a b {"c" (inc a)}]))
```

License
-------

All the code is licensed under the GNU Lesser General Public License
(v3+).
