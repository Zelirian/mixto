# Mixto: A simple mixin superclass
[![CI](https://github.com/atom/mixto/actions/workflows/ci.yml/badge.svg)](https://github.com/atom/mixto/actions/workflows/ci.yml)

To create a mixin, subclass mixto:

```coffee
Mixin = require 'mixto'

class MyMixin extends Mixin
  @classMethod: -> console.log("foo")
  instanceMethod: -> console.log("bar")
```

Then mix into classes with `.includeInto`:

```coffee
class MyClass
  MyMixin.includeInto(this)

MyClass.classMethod()
(new MyClass).instanceMethod()
```

Or extend individual objects with `.extend`:

```coffee-script
myObject = {a: 1, b: 2}
MyMixin.extend(myObject)
myObject.instanceMethod()
```

Or build standalone instances of your 'mixin':

```
standalone = new MyMixin
standalone.instanceMethod()
```
