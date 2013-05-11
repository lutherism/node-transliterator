# Transliterator

A node module that transforms strings that contain cyrillic characters into ascii compliant text.  node-transliterator has the ability to replace characters with codes not normally viewable.

An example use case is when you have parsed a string, and it contains an emoji.  node-transliterator will remove the emoji if you pass in the string.

Another use case is URL slugs.

## Installation

```javascript
npm install transliterator --save
```

## API

```javascript
var transliterator = require('transliterator');
```

* `transliterator(string, [replacement])`

```javascript
transliterator('źebŕa') // 'zebra'
transliterator('ǿ\'doules.') // 'o\'doules.'
transliterator('i hatè véggiês') // 'i hate veggies'

transliterator('a') // 'a'
transliterator('harǤold') // 'harold'
transliterator('䫸 is ŗŒ') // ' is rOE'

transliterator('', 'h') // 'h'
transliterator('Ⓩbad ሏ', '_') // '_bad _'
transliterator('պ պ պ պ', '_') // '_ _ _ _'
```