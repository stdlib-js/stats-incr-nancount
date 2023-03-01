<!--

@license Apache-2.0

Copyright (c) 2020 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->

# incrnancount

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Compute a count incrementally, ignoring `NaN` values.



<section class="usage">

## Usage

To use in Observable,

```javascript
incrnancount = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-incr-nancount@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var incrnancount = require( 'path/to/vendor/umd/stats-incr-nancount/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/stats-incr-nancount@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.incrnancount;
})();
</script>
```

#### incrnancount()

Returns an accumulator `function` which incrementally computes a count, ignoring `NaN` values.

```javascript
var accumulator = incrnancount();
```

#### accumulator( \[x] )

If provided an input value `x`, the accumulator function returns an updated count. If not provided an input value `x`, the accumulator function returns the current count.

```javascript
var accumulator = incrnancount();

var count = accumulator( 2.0 );
// returns 1

count = accumulator( 1.0 );
// returns 2

count = accumulator( NaN );
// returns 2

count = accumulator( 3.0 );
// returns 3

count = accumulator();
// returns 3
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/random-base-randu@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/stats-incr-nancount@umd/browser.js"></script>
<script type="text/javascript">
(function () {

var accumulator;
var v;
var i;

// Initialize an accumulator:
accumulator = incrnancount();

// For each simulated datum, update the count...
for ( i = 0; i < 100; i++ ) {
    if ( randu() < 0.2 ) {
        v = NaN;
    } else {
        v = randu() * 100.0;
    }
    accumulator( v );
}
console.log( accumulator() );

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/stats-incr/nansum`][@stdlib/stats/incr/nansum]</span><span class="delimiter">: </span><span class="description">compute a sum incrementally, ignoring NaN values.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/stats-incr-nancount.svg
[npm-url]: https://npmjs.org/package/@stdlib/stats-incr-nancount

[test-image]: https://github.com/stdlib-js/stats-incr-nancount/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/stats-incr-nancount/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/stats-incr-nancount/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/stats-incr-nancount?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/stats-incr-nancount.svg
[dependencies-url]: https://david-dm.org/stdlib-js/stats-incr-nancount/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/stats-incr-nancount/tree/deno
[umd-url]: https://github.com/stdlib-js/stats-incr-nancount/tree/umd
[esm-url]: https://github.com/stdlib-js/stats-incr-nancount/tree/esm
[branches-url]: https://github.com/stdlib-js/stats-incr-nancount/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/stats-incr-nancount/main/LICENSE

<!-- <related-links> -->

[@stdlib/stats/incr/nansum]: https://github.com/stdlib-js/stats-incr-nansum/tree/umd

<!-- </related-links> -->

</section>

<!-- /.links -->
