# Author - Khalifa Bako

# 0x13. JavaScript - Objects, Scopes and Closures

## GENERAL :open_book::open_book::open_book::

 <ol>
	<li>Why JavaScript programming is amazing</li>
	<li>How to create an object in JavaScript</li>
	<li>What <code>this</code> means</li>
	<li>What <code>undefined</code> means </li>
	<li>Why the variable type and scope is important</li>
	<li>What is a closure</li>
	<li>What is a prototype</li>
	<li>How to inherit an object from another</li>
</ol>

## RESOURCES:

 <ol>
	<li><a href="/rltoken/OJ4pU6uHwfCrAclbZsk_Hg" title="JavaScript object basics" target="_blank">JavaScript object basics</a> </li>
	<li><a href="/rltoken/Uqv-UMsBUpHWQZXBf5fn0g" title="Object-oriented JavaScript" target="_blank">Object-oriented JavaScript</a> (<em><strong>read all examples!</strong></em>)</li>
	<li><a href="/rltoken/zMWxOmGWEsOCldCKeDswCA" title="Class - ES6" target="_blank">Class - ES6</a> </li>
	<li><a href="/rltoken/DTMKogwFYEgUnpLrNvTcfQ" title="super - ES6" target="_blank">super - ES6</a> </li>
	<li><a href="/rltoken/fh2JHfNNa-HLnmfSdOo9TA" title="extends - ES6" target="_blank">extends - ES6</a> </li>
	<li><a href="/rltoken/lrlwnQMM82RimJJcfLao5w" title="Object prototypes" target="_blank">Object prototypes</a> </li>
	<li><a href="/rltoken/LDpXxzBrdmmXAHoNrWwLxg" title="Inheritance in JavaScript" target="_blank">Inheritance in JavaScript</a> </li>
	<li><a href="/rltoken/qDa7F8060Jlhe3DZZitY4A" title="Closures" target="_blank">Closures</a> </li>
	<li><a href="/rltoken/ockP7FQKKmTRvfeAHw-XSw" title="this/self" target="_blank">this/self</a> </li>
	<li><a href="/rltoken/22mdHf9KeFhRQrLP-e1hPw" title="Modern JS" target="_blank">Modern JS</a> </li>
</ol>

## INTRODUCTION TO FILES :closed_book::closed_book::closed_book::

0.	[**0-rectangle.js**:](#0-rectanglejs) An empty class <code>Rectangle</code> that defines a rectangle
1.	[**1-rectangle.js**:](#1-rectanglejs) Class <code>Rectangle</code> that defines a rectangle
2.	[**2-rectangle.js**:](#2-rectanglejs) Class <code>Rectangle</code> that defines a rectangle
3.	[**3-rectangle.js**:](#3-rectanglejs) Class <code>Rectangle</code> that defines a rectangle
4.	[**4-rectangle.js**:](#4-rectanglejs) Class <code>Rectangle</code> that defines a rectangle
5.	[**5-square.js**:](#5-squarejs) Class <code>Square</code> that defines a square and inherits from <code>Rectangle</code> of <code>4-rectangle.js</code>
6.	[**6-square.js**:](#6-squarejs) Class <code>Square</code> that defines a square and inherits from <code>Square</code> of <code>5-square.js</code>
7.	[**7-occurrences.js**:](#7-occurrencesjs) Function that returns the number of occurrences in a list
8.	[**8-esrever.js**:](#8-esreverjs) Function that returns the reversed version of a list
9.	[**9-logme.js**:](#9-logmejs) Function that prints the number of arguments already printed and the new argument value. (see example below)
10.	[**10-converter.js**:](#10-converterjs) Function that converts a number from base 10 to another base passed as argument
11.	[**100-map.js**:](#100-mapjs) Script that imports an array and computes a new array.
12.	[**101-sorted.js**:](#101-sortedjs) Script that imports a dictionary of occurrences by user id and computes a dictionary of user ids by occurrence.

## FILES :bookmark_tabs::bookmark_tabs::bookmark_tabs::

### 0-rectangle.js

**<p>An empty class <code>Rectangle</code> that defines a rectangle</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 0-main.js
#!/usr/bin/node
const Rectangle = require('./0-rectangle');

const r1 = new Rectangle();
console.log(r1);
console.log(r1.constructor);

guillaume@ubuntu:~/0x13$ ./0-main.js
Rectangle {}
[Function: Rectangle]
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 1-rectangle.js

**<p>Class <code>Rectangle</code> that defines a rectangle</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 1-main.js
#!/usr/bin/node
const Rectangle = require('./1-rectangle');

const r1 = new Rectangle(2, 3);
console.log(r1);
console.log(r1.width);
console.log(r1.height);

const r2 = new Rectangle(2, -3);
console.log(r2);
console.log(r2.width);
console.log(r2.height);

const r3 = new Rectangle(2);
console.log(r3);
console.log(r3.width);
console.log(r3.height);

guillaume@ubuntu:~/0x13$ ./1-main.js
Rectangle { width: 2, height: 3 }
2
3
Rectangle { width: 2, height: -3 }
2
-3
Rectangle { width: 2, height: undefined }
2
undefined
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 2-rectangle.js

**<p>Class <code>Rectangle</code> that defines a rectangle</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 2-main.js
#!/usr/bin/node
const Rectangle = require('./2-rectangle');

const r1 = new Rectangle(2, 3);
console.log(r1);
console.log(r1.width);
console.log(r1.height);

const r2 = new Rectangle(2, -3);
console.log(r2);
console.log(r2.width);
console.log(r2.height);

const r3 = new Rectangle(2);
console.log(r3);
console.log(r3.width);
console.log(r3.height);

const r4 = new Rectangle(2, 0);
console.log(r4);
console.log(r4.width);
console.log(r4.height);

guillaume@ubuntu:~/0x13$ ./2-main.js
Rectangle { width: 2, height: 3 }
2
3
Rectangle {}
undefined
undefined
Rectangle {}
undefined
undefined
Rectangle {}
undefined
undefined
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 3-rectangle.js

**<p>Class <code>Rectangle</code> that defines a rectangle</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 3-main.js
#!/usr/bin/node
const Rectangle = require('./3-rectangle');

const r1 = new Rectangle(2, 3);
r1.print();

const r2 = new Rectangle(10, 5);
r2.print();

guillaume@ubuntu:~/0x13$ ./3-main.js
XX
XX
XX
XXXXXXXXXX
XXXXXXXXXX
XXXXXXXXXX
XXXXXXXXXX
XXXXXXXXXX
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 4-rectangle.js

**<p>Class <code>Rectangle</code> that defines a rectangle</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 4-main.js
#!/usr/bin/node
const Rectangle = require('./4-rectangle');

const r1 = new Rectangle(2, 3);
console.log('Normal:');
r1.print();

console.log('Double:');
r1.double();
r1.print();

console.log('Rotate:');
r1.rotate();
r1.print();

guillaume@ubuntu:~/0x13$ ./4-main.js
Normal:
XX
XX
XX
Double:
XXXX
XXXX
XXXX
XXXX
XXXX
XXXX
Rotate:
XXXXXX
XXXXXX
XXXXXX
XXXXXX
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 5-square.js

**<p>Class <code>Square</code> that defines a square and inherits from <code>Rectangle</code> of <code>4-rectangle.js</code></p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 5-main.js
#!/usr/bin/node
const Square = require('./5-square');

const s1 = new Square(4);
s1.print();
s1.double();
s1.print();

guillaume@ubuntu:~/0x13$ ./5-main.js
XXXX
XXXX
XXXX
XXXX
XXXXXXXX
XXXXXXXX
XXXXXXXX
XXXXXXXX
XXXXXXXX
XXXXXXXX
XXXXXXXX
XXXXXXXX
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 6-square.js

**<p>Class <code>Square</code> that defines a square and inherits from <code>Square</code> of <code>5-square.js</code></p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 6-main.js
#!/usr/bin/node
const Square = require('./6-square');

const s1 = new Square(4);
s1.charPrint();

s1.charPrint('C');

guillaume@ubuntu:~/0x13$ ./6-main.js
XXXX
XXXX
XXXX
XXXX
CCCC
CCCC
CCCC
CCCC
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 7-occurrences.js

**<p>Function that returns the number of occurrences in a list</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 7-main.js
#!/usr/bin/node
const nbOccurences = require('./7-occurrences').nbOccurences;

console.log(nbOccurences([1, 2, 3, 4, 5, 6], 3));
console.log(nbOccurences([3, 2, 3, 4, 5, 3, 3], 3));
console.log(nbOccurences(["H", 12, "c", "H", "Holberton", 8], "H"));

guillaume@ubuntu:~/0x13$ ./7-main.js
1
4
2
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 8-esrever.js

**<p>Function that returns the reversed version of a list</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 8-main.js
#!/usr/bin/node
const esrever = require('./8-esrever').esrever;

console.log(esrever([1, 2, 3, 4, 5]));
console.log(esrever(["Holberton", 89, { id: 12 }, "String"]));

guillaume@ubuntu:~/0x13$ ./8-main.js
[ 5, 4, 3, 2, 1 ]
[ 'String', { id: 12 }, 89, 'Holberton' ]
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 9-logme.js

**<p>Function that prints the number of arguments already printed and the new argument value. (see example below)</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 9-main.js
#!/usr/bin/node
const logMe = require('./9-logme').logMe;

logMe("Hello");
logMe("Holberton");
logMe("School");

guillaume@ubuntu:~/0x13$ ./9-main.js
0: Hello
1: Holberton
2: School
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 10-converter.js

**<p>Function that converts a number from base 10 to another base passed as argument</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 10-main.js
#!/usr/bin/node
const converter = require('./10-converter').converter;

let myConverter = converter(10);

console.log(myConverter(2));
console.log(myConverter(12));
console.log(myConverter(89));


myConverter = converter(16);

console.log(myConverter(2));
console.log(myConverter(12));
console.log(myConverter(89));

guillaume@ubuntu:~/0x13$ ./10-main.js
2
12
89
2
c
59
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 100-map.js

**<p>Script that imports an array and computes a new array.</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 100-data.js
#!/usr/bin/node
exports.list = [1, 2, 3, 4, 5];
guillaume@ubuntu:~/0x13$ ./100-map.js 
[ 1, 2, 3, 4, 5 ]
[ 0, 2, 6, 12, 20 ]
guillaume@ubuntu:~/0x13$ 
</code></pre>

### 101-sorted.js

**<p>Script that imports a dictionary of occurrences by user id and computes a dictionary of user ids by occurrence.</p>**

<pre><code>guillaume@ubuntu:~/0x13$ cat 101-data.js
#!/usr/bin/node
exports.dict = {
  89: 1,
  90: 2,
  91: 1,
  92: 3,
  93: 1,
  94: 2
};
guillaume@ubuntu:~/0x13$ ./101-sorted.js 
{ '1': [ '89', '91', '93' ], '2': [ '90', '94' ], '3': [ '92' ] }
guillaume@ubuntu:~/0x13$ 
</code></pre>

