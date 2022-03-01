<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

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

# isWritableProperty

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Test if an object's own property is writable.

<section class="installation">

## Installation

```bash
npm install @stdlib/assert-is-writable-property
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm` branch][esm-url].
-   If you are using Deno, visit the [`deno` branch][deno-url].
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd` branch][umd-url].

</section>

<section class="usage">

## Usage

```javascript
var isWritableProperty = require( '@stdlib/assert-is-writable-property' );
```

#### isWritableProperty( value, property )

Returns a `boolean` indicating if a `value` has a writable `property`.

<!-- eslint-disable no-restricted-syntax -->

```javascript
var defineProperty = require( '@stdlib/utils-define-property' );

var obj = {
    'foo': 'bar'
};

defineProperty( obj, 'beep', {
    'configurable': false,
    'enumerable': false,
    'writable': false,
    'value': 'boop'
});

defineProperty( obj, 'setter', {
    'configurable': false,
    'enumerable': false,
    'set': function setter( v ) {
        obj.foo = v;
    }
});

var bool = isWritableProperty( obj, 'foo' );
// returns true

bool = isWritableProperty( obj, 'setter' );
// returns true

bool = isWritableProperty( obj, 'beep' );
// returns false
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   Value arguments other than `null` or `undefined` are coerced to `objects`.

    ```javascript
    var bool = isWritableProperty( 'beep', 'length' );
    // returns false
    ```

-   Property arguments are coerced to `strings`.

    ```javascript
    var obj = {
        'null': 'foo'
    };

    var bool = isWritableProperty( obj, null );
    // returns true
    ```

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint-disable object-curly-newline -->

<!-- eslint no-undef: "error" -->

```javascript
var isWritableProperty = require( '@stdlib/assert-is-writable-property' );

var bool = isWritableProperty( [ 'a' ], 'length' );
// returns true

bool = isWritableProperty( { 'a': 'b' }, 'a' );
// returns true

bool = isWritableProperty( [ 'a' ], 0 );
// returns true

bool = isWritableProperty( { 'null': false }, null );
// returns true

bool = isWritableProperty( { '[object Object]': false }, {} );
// returns true

bool = isWritableProperty( {}, 'toString' );
// returns false

bool = isWritableProperty( {}, 'hasOwnProperty' );
// returns false

bool = isWritableProperty( null, 'a' );
// returns false

bool = isWritableProperty( void 0, 'a' );
// returns false
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/assert/is-readable-property`][@stdlib/assert/is-readable-property]</span><span class="delimiter">: </span><span class="description">test if an object's own property is readable.</span>
-   <span class="package-name">[`@stdlib/assert/is-read-write-property`][@stdlib/assert/is-read-write-property]</span><span class="delimiter">: </span><span class="description">test if an object's own property is readable and writable.</span>
-   <span class="package-name">[`@stdlib/assert/is-writable-property-in`][@stdlib/assert/is-writable-property-in]</span><span class="delimiter">: </span><span class="description">test if an object's own or inherited property is writable.</span>
-   <span class="package-name">[`@stdlib/assert/is-write-only-property`][@stdlib/assert/is-write-only-property]</span><span class="delimiter">: </span><span class="description">test if an object's own property is write-only.</span>

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

Copyright &copy; 2016-2022. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/assert-is-writable-property.svg
[npm-url]: https://npmjs.org/package/@stdlib/assert-is-writable-property

[test-image]: https://github.com/stdlib-js/assert-is-writable-property/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/assert-is-writable-property/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/assert-is-writable-property/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/assert-is-writable-property?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/assert-is-writable-property.svg
[dependencies-url]: https://david-dm.org/stdlib-js/assert-is-writable-property/main

-->

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/assert-is-writable-property/tree/deno
[umd-url]: https://github.com/stdlib-js/assert-is-writable-property/tree/umd
[esm-url]: https://github.com/stdlib-js/assert-is-writable-property/tree/esm

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/assert-is-writable-property/main/LICENSE

<!-- <related-links> -->

[@stdlib/assert/is-readable-property]: https://github.com/stdlib-js/assert-is-readable-property

[@stdlib/assert/is-read-write-property]: https://github.com/stdlib-js/assert-is-read-write-property

[@stdlib/assert/is-writable-property-in]: https://github.com/stdlib-js/assert-is-writable-property-in

[@stdlib/assert/is-write-only-property]: https://github.com/stdlib-js/assert-is-write-only-property

<!-- </related-links> -->

</section>

<!-- /.links -->
