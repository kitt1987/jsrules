# **DO NOT** create and return the new object in a function.

> The **bad** way

b.js
```javascript
exports = module.exports = function(args) {
	// !! Create and return the new object
	return new Sth(args);
};

Function Sth(args) {
	
}
```

a.js
```javascript
var SthBuilder = require('./b.js');

var x = SthBuilder({/* args */});
```

> The **geeky** way

b.js
```javascript
exports.Sth = Sth;

Function Sth(args) {
	
}
```

a.js
```javascript
var Sth = require('./b.js').Sth;

var x = new Sth({/* args */});
```