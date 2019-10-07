# lum.spjs.php

## Summary

Statistical Processing for JSON Structures

A really minimal data processing library that I've used in a couple projects.
You pass it a data set (returned from say a CSV file) which is an array of
associative arrays, and then pass it an array of statements (which themselves
are an array of associative arrays defining rules to apply to the data.)

## Classes

| Class                   | Description                                       |
| ----------------------- | ------------------------------------------------- |
| Lum\SPJS                | The SPJS processor.                               |

## Example

### Initial Data

```json
[
  {"id":1, "ctype":1},
  {"id":2, "ctype":1},
  {"id":3, "ctype":5},
  {"id":4, "ctype":3},
  {"id":5, "ctype":6}
]
```

## Statements

```json
[
  {"always": true, "set": {"rtype": 0}},
  {"if":{"ctype":[1,2,5]}, "set": {"rtype": 1}},
  {"if":{"ctype":[3,4]}, "set": {"rtype": 2}}
]
```

### Processed Data

```json
[
  {"id":1, "ctype":1, "rtype": 1},
  {"id":2, "ctype":1, "rtype": 1},
  {"id":3, "ctype":5, "rtype": 1},
  {"id":4, "ctype":3, "rtype": 2},
  {"id":5, "ctype":6, "rtype": 0}
]
```

## TODO

Write tests.

## Official URLs

This library can be found in two places:

 * [Github](https://github.com/supernovus/lum.spjs.php)
 * [Packageist](https://packagist.org/packages/lum/lum-spjs)

## Author

Timothy Totten

## License

[MIT](https://spdx.org/licenses/MIT.html)
