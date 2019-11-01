# jmespath.js

> **NOTE:** This is a fork of jmespath.js. The original does
> not appear to be actively maintained - please see our
> contribution guidelines for more details.

## Introduction

jmespath.js is a javascript implementation of JMESPath,
which is a query language for JSON.  It will take a JSON
document and transform it into another JSON document
through a JMESPath expression.

Using jmespath.js is really easy.  There's a single function
you use, `jmespath.search`:


```
> var jmespath = require('jmespath');
> jmespath.search({foo: {bar: {baz: [0, 1, 2, 3, 4]}}}, "foo.bar.baz[2]")
2
```

In the example we gave the ``search`` function input data of
`{foo: {bar: {baz: [0, 1, 2, 3, 4]}}}` as well as the JMESPath
expression `foo.bar.baz[2]`, and the `search` function evaluated
the expression against the input data to produce the result ``2``.

The JMESPath language can do a lot more than select an element
from a list.  Here are a few more examples:

```
> jmespath.search({foo: {bar: {baz: [0, 1, 2, 3, 4]}}}, "foo.bar")
{ baz: [ 0, 1, 2, 3, 4 ] }

> jmespath.search({"foo": [{"first": "a", "last": "b"},
                           {"first": "c", "last": "d"}]},
                  "foo[*].first")
[ 'a', 'c' ]

> jmespath.search({"foo": [{"age": 20}, {"age": 25},
                           {"age": 30}, {"age": 35},
                           {"age": 40}]},
                  "foo[?age > `30`]")
[ { age: 35 }, { age: 40 } ]
```

## Installation

```bash
npm install @gorillastack/jmespath
```

## More Resources

The example above only show a small amount of what
a JMESPath expression can do.  If you want to take a
tour of the language, the *best* place to go is the
[JMESPath Tutorial](https://gorillastack-jmespath.netlify.com/tutorial.html).

One of the best things about JMESPath is that it is
implemented in many different programming languages including
python, ruby, php, lua, etc.  To see a complete list of libraries,
check out the [JMESPath libraries page](https://gorillastack-jmespath.netlify.com/libraries.html).

And finally, the full JMESPath specification can be found
on the [JMESPath site](https://gorillastack-jmespath.netlify.com/specification.html).

## Contributing

Although this is a copy of the original jmespath.js repository, we are
accepting contributions!

Please see our [Contribution Guidelines](CONTRIBUTING.md) and our
[Code of Conduct](CODE_OF_CONDUCT.md).
