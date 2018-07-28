# Lab62
<p>
  <a href="https://travis-ci.org/harmankang/Lab62"><img src="https://travis-ci.org/harmankang/Lab62.svg?branch=master"></a>
  <a href="https://github.com/harmankang/Lab62/issues"><img src="https://img.shields.io/github/issues/harmankang/Lab62.svg"></a>
  <a href="https://harmankang.github.io/web-demos/Lab62/Lab62.html"><img src="https://img.shields.io/badge/try-demo-blue.svg"></a>
  <a href="https://github.com/harmankang/Lab62/blob/master/LICENSE"><img src="https://img.shields.io/github/license/harmankang/Lab62.svg"></a>
</p>

<p>A quick way to create short, unique, and human readable IDs.</p>

(Based on my original [Swift implementation](https://github.com/harmankang/b62_IDs))

### Use
```js
let e = new Lab62(); 
e.make(6) // wOWLXk
```
> You can pass a length value to `make()`

If you are unsure of many characters to use, read [the explanation](#explanation) for context.
### Access

Clone it
```
git clone https://github.com/harmankang/Lab62.git
```

Or you can download and include [the source file](https://github.com/harmankang/Lab62/blob/master/src/Lab62) in your project. It's not a very large file (at just 939 Bytes).

### Testing the uniqueness
I looped `Lab62` 10 times using the following code.

```js
for (var i = 0; i < 10; i++) {
 let gen = new Lab62();
 console.log(gen.make(6));
}
```
This was the output:

```
p36sWO
mc580S
anKeWa
NrUtCI
OiYGDR
PiR6pJ
MMIljE
UbNgaM
Pym5x8
MtEuHW
```

### Why
I originally wrote the [Swift implementation](https://github.com/harmankang/b62_IDs) because I needed short and unique ids that didn't look suspicious.

I needed a javascript version to generate these ids in a browser.

### Explanation
If you generate a 6 character random string, then there are 62<sup>6</sup> = 56,800,235,584 possible combinations of the base 62 character set. That means if you generated a unique id once every second, it would take more than 657,000 days, or 1800+ years, to run out (please see my [warning](#warning)).

The [character set](https://github.com/harmankang/Lab62/) I use is alphanumerical. Including both upper and lower cases, there are 62 alphanumerical characters in the set. 

I looked into Base64 encoding, but it gives `/`'s and that is not acceptable for URL use-cases.

#### More reading

I explain the origin of this project in more detail in my blog post, [Human Readable IDs](https://h13g.com/read?id=28).

### Warning

I should warn you that there is no guarantee that `Lab62` will be collision proof. You should use a database to keep track of existing ids.

### License
MIT

