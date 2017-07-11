# json
A JSON variant

This is a WIP of various ideas. Current ideas here might conflict or be unworkable. It's designed to work with: https://github.com/sirisian/ecmascript-types

* Use backtick \` for quotes and allow them optionally for members
* Basic comments using /* */ syntax
* Support for basic float (N.N, -N.N), integer (N, -N), hex (including 64-bit types), and bool
* Support for color formats: #fff, #ffffff, #ffffffff, rgb(255, 255, 255), and rgba(255, 255, 255, 0.5)
* Designed to be whitespace independent
* Typed keys using "name:Type: value" syntax
* Types:

```
number
bool
string
object
symbol
int8/16/32/64
uint8/16/32/64
bigint
float16/32/64/80/128
decimal32/64/128
bool8x16/16x8/32x4/64x2/8x32/16x16/32x8/64x4
int8x16/16x8/32x4/64x2/8x32/16x16/32x8/64x4
uint8x16/16x8/32x4/64x2/8x32/16x16/32x8/64x4
float32x4/64x2/32x8/64x4
rational
complex
any
void
```

```js
{
	foo: `bar'"baz`,
	a b:
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
	12.2:float32: `foo` /* values don't have to match the type */
}
```

ECMAScript syntax:
```js
JSON.encode({});
JSON.decode(`{}`);
```
