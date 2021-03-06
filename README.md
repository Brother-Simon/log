# mongodb-log

[![build status](https://secure.travis-ci.org/mongodb-js/log.png)](http://travis-ci.org/mongodb-js/log)
[![Coverage Status](https://coveralls.io/repos/mongodb-js/log/badge.svg)](https://coveralls.io/r/mongodb-js/log)

Normalize MongoDB log entries into objects that make sense.

## Example

```javascript
var parse = require('mongodb-log');
var fs = require('fs');
var es = require('event-stream');

fs.createReadStream('/var/log/mongodb/mongod.log')
  .pipe(es.split('\n'))
  .pipe(parse())
  .pipe(fs.createWriteStream('/var/log/mongodb/mongod.json'));
```

## License

MIT

