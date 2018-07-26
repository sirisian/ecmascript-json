# json
A JSON variant

This is a WIP of various ideas. Current ideas here might conflict or be unworkable. It's designed to work with: https://github.com/sirisian/ecmascript-types

* Use backtick \` for quotes and allow them optionally for members
* Basic comments using /* */ syntax
* Support for basic float (N.N, -N.N), integer (N, -N), hex (including 64-bit types), and bool
* Support for color formats: #fff, #ffffff, #ffffffff, rgb(255, 255, 255), and rgba(255, 255, 255, 0.5)
* Designed to be whitespace independent
* Typed keys using "(name:Type): value" syntax
* Object constructor syntax (name:Type): (arguments...)
* Supports arrow functions?
* Types:

```number```  
```boolean```  
```string```  
```object```  
```symbol```  
```int8```, ```int16```, ```int32```, ```int64```  
```uint8```, ```uint16```, ```uint32```, ```uint64```  
```bigint```  
```float16```, ```float32```, ```float64```, ```float80```, ```float128```  
```decimal32```, ```decimal64```, ```decimal128```  
```boolean8x16```, ```boolean16x8```, ```boolean32x4```, ```boolean64x2```, ```boolean8x32```, ```boolean16x16```, ```boolean32x8```, ```boolean64x4```  
```int8x16```, ```int16x8```, ```int32x4```, ```int64x2```, ```int8x32```, ```int16x16```, ```int32x8```, ```int64x4```  
```uint8x16```, ```uint16x8```, ```uint32x4```, ```uint64x2```, ```uint8x32```, ```uint16x16```, ```uint32x8```, ```uint64x4```  
```float32x4```, ```float64x2```, ```float32x8```, ```float64x4```  
```rational```  
```complex```  
```any```  
```void```  

```js
{
	foo: `bar'"baz`,
	a:
	[
		#fff,
		#ffffff,
		#ffffffff,
		rgb(255, 255, 255),
		rgba(255, 255, 255, 0.5)
	],
	foobar: 0x1,
	bar: 2.5,
	baz: 4,
	/* comment */
	bool: true,
	0123: `string`
	`string`:string:
	(12.2:float32): `foo`, /* values don't have to match the type */
	(foo:float32x4): (0, 0, 1, 1)
}
```

ECMAScript syntax:
```js
JSON.encode({});
JSON.decode(`{}`);
```
