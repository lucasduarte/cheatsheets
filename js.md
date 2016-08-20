#Javascript

## Factory Function
```js
	var createCounter = function() {
		var value = 0;
		return {
			add: function () {
				return ++value;
			}
		};
	};

	var counter = createCounter()

```

## Constructor Function
```js
	var Counter = function() {
		var value = 0;
		this.add = function () {
			return ++value;
		};
	};

	var counter = new Counter();
```

## Module Pattern
```js
	var counter = (function() {
		var value = 0;
		return {
			add: function() {
				return ++value;
			}
		};
	})();
```

## Revealing Module Pattern
```js
	var counter = (function (){
		var _value = 0;
		var _add = function() {
			return ++_value;
		};
		var _reset = function() {
			_value = 0;
		};
		return {
			add: _add,
			reset: _reset
		};
	})();
```
