### String.length 

It'll return the length of the string and the counting starts from 1. For an empty string the length of the string will be zero(0).

``` js
* example: 
    let str = "abcd";
    console.log(str.length); // Output: 4
    
```

### String.toUpperCase()

This method returns the value of the string converted to upper case. It does not affect the value of the string.

``` js
* example: 
    let str = "hello";
    console.log(str.toUpperCase()); // Output: "HELLO"
    
```

### String.toLowerCase()

This method returns the value of the string converted to lower case. It does not affect the value of the string.

``` js
* example: 
    let str = "HELLO";
    console.log(str.toUpperCase()); // Output: "hello"
    
```
### String.fromCharCode(code1, code2, . . .)

This method gives a character by its UTF-16 code. 

``` js
* example: 

    console.log( String.fromCharCode(65, 66, 67) );  // Output: "ABC"
    console.log( String.fromCharCode(97) );  // Output: "a"
    
```

### String.fromCodePoint(code1, code2, . . .)

This method also gives a character by its UTF-16 code like String.fromCharCode(code). The only difference is it supports "surrogate pairs".

``` js
* example: 

    console.log( String.fromCodePoint(65, 67) );  // Output: "AC"
    console.log( String.fromCodePoint(97) );  // Output: "a"
    
```


### Surrogate Pairs : 

Symbols like emojis are encoded with a pair of 2-byte characters        called “a surrogate pair”. Length of such symbol is 2.
    
    '😂'.length   

``` js
* example: 

    console.log( '😂'.length );  // Output: 2
    console.log( '𩷶'.length );  // Output: 2
    
```

### String.prototype.codePointAt(pos)

This method returns a non-negative integer that is Unicode code point. Here pos is the index of that element from the given string whose Unicode code point value you want to know. It can also deal with "surrogate pairs". If there is no element at specified position it'll return undefined.

``` js
* example: 
    let str = "AltCampus";
    console.log( str.codePointAt(2) );  // Output: 116
    console.log( str.codePointAt(3) );  // Output: 67
    console.log( str.codePointAt(50) );  // Output: undefined
    
```

### String.charCodeAt(pos)

This method also returns a non-negative integer between 0 and 65535 representing the UTF-16 code unit like String.prototype.codePointAt(pos). The only difference is it does not support "surrogate pairs".

``` js
* example: 

    console.log( String.fromCodePoint(65, 67) );  // Output: "AC"
    console.log( String.fromCodePoint(97) );  // Output: "a"
    
```


### String.prototype.charAt(pos)

This method returns the character from the string whose index is equal to pos. By default the value of pos is 0. If pos is out of range it'll return an empty string. If the value of pos can not be converted to integer by default it'll take zero.

``` js
* example: 
    let str = "Hello World!"
    console.log( str.charAt(1) );  // Output: "e"
    console.log( str.charAt(200) );  // Output: ""
    console.log( str.charAt("a") );  // Output: "H"
    
```


### String.prototype.indexOf(ch, pos)

This method returns the index of the first occurrence of the specified value within string. If the value is not found it'll return -1. Here pos is the starting index from where it looks for the specific value.

``` js
* example: 
    let str = "Hello World!"
    console.log( str.indexOf("e") );  // Output: 1
    console.log( str.indexOf("l") );  // Output: 2
    console.log( str.indexOf("o") );  // Output: 4

    console.log( str.indexOf("Hello") );  // Output: 0
    console.log( str.indexOf("World") );  // Output: 6

    console.log( str.indexOf("z") );  // Output: -1
    
```

### String.prototype.lastIndexOf(ch, pos)

It similar to String.prototype.indexOf(ch, pos). The difference between these two method is that it searches from the end of a string to its beginning and would list the occurrences in the reverse order. 

It returns the index of the last occurrence of the specified value but from the end (Right to Left).

``` js
* example: 
    let str = "Hello World!"
    console.log( str.lastIndexOf("e") );  // Output: 1
    console.log( str.lastIndexOf("l") );  // Output: 9
    console.log( str.lastIndexOf("o") );  // Output: 7

    console.log( str.lastIndexOf("Hello") );  // Output: 0
    console.log( str.lastIndexOf("World") );  // Output: 6

    console.log( str.lastIndexOf("z") );  // Output: -1
    
```

### String.prototype.includes(sub)

It looks for a specific substring i.e. sub within the given string. If the desired substring is found it returns true (Boolean) else it returns false (Boolean).

``` js
* example: 
    let str = "HelloWorld!"
    console.log( str.includes("H") );  // Output: true
    console.log( str.includes("Hello") );  // Output: true
    console.log( str.includes("!") );  // Output: true
    
    console.log( str.includes("") );  // Output: true
    console.log( str.includes("Random Text") );  // Output: false
     
```

### String.prototype.endsWith(sub)

It checks whether the given string ends with the specific sub-string i.e. sub. 

``` js
* example: 
    let str = "HelloWorld!"
    console.log( str.endsWith("H") );  // Output: true
    console.log( str.endsWith("Hello") );  // Output: true
    console.log( str.endsWith("!") );  // Output: true
    
    console.log( str.endsWith("") );  // Output: true
    console.log( str.endsWith(" ") );  // Output: false

    console.log( str.endsWith("Random Text") );  // Output: false
     
```

### String.prototype.startsWith(sub)

It checks whether the given string starts with the specific sub-string i.e. sub. 

``` js
* example: 
    let str = "HelloWorld!"
    console.log( str.startsWith("H") );  // Output: true
    console.log( str.startsWith("Hello") );  // Output: true
    console.log( str.startsWith("!") );  // Output: false
    
    console.log( str.startsWith("") );  // Output: true
    console.log( str.startsWith(" ") );  // Output: false
    
    console.log( str.startsWith("Random Text") );  // Output: false
     
```

### String.prototype.slice(startIndex, endIndex)

It returns extracted part of the given string. It does not change the original string.

* If the startIndex is negative then it'll treated as (String.length - startIndex)
* The character at endIndex will not be included.
* If the endIndex is negative then it'll treated as (String.length - endIndex)
* If endIndex is omitted, slice() extracts to the end of the string.
* If the startIndex and endIndex is not an integer or not valid
  (startIndex > string.length) then it'll return an empty string.

``` js
* example: 
    let str = "Hello-World!"
    console.log( str.slice(0,5) );  // Output: "Hello"
    
    console.log( str.startsWith(7,-2) );  // Output: "orl"
    console.log( str.startsWith(-3,12) );  // Output: "ld"
    
    console.log( str.slice(6) );  // Output: "World"
    
    
    console.log( str.slice(50,50) );  // Output: ""
    console.log( str.slice("a", "b") );  // Output: ""

    console.log( str.slice("a", 5) );  // Output: "Hello"
    console.log( str.slice("", 5) );  // Output: "Hello"

    console.log( str.slice("a") );  // Output: "Hello-World"
    console.log( str.slice("") );  // Output: "Hello-World"
     
```

### String.prototype.substring(indexStart, indexEnd)

This method returns the part of the string between the start and end indexes.
* The character at indexEnd will not be included.
* If indexEnd is omitted, substring() extracts characters to the end of the string.
* If indexStart is equal to indexEnd, substring() returns an empty string.
* If indexStart is greater than indexEnd, then the effect of substring() is as if the two arguments were swapped.
* Any argument value that is less than 0 or greater than stringName.length is treated as if it were 0 and stringName.length, respectively.
* Any argument value that is NaN is treated as if it were 0.


``` js
* example: 
    let str = "Hello-World!"
    console.log( str.substring(0,5) );  // Output: "Hello"
    
    console.log( str.substring(7,-2) );  // Output: "Hello-W"
    console.log( str.substring(-3,12) );  // Output: "Hello-World!"
    
    console.log( str.substring(6) );  // Output: "World"

    console.log( str.substring(5,5) );  // Output: ""
    console.log( str.substring(6,0) );  // Output: "Hello-"
    
    
    console.log( str.substring(50,50) );  // Output: ""
    console.log( str.substring("a", "b") );  // Output: ""

    console.log( str.slisubstringce("a", 5) );  // Output: "error"
    console.log( str.substring("", 5) );  // Output: "Hello"

    console.log( str.substring("a") );  // Output: "TypeError: str.substringce is not a function"
    console.log( str.substring("") );  // Output: "TypeError: str.substringce is not a function"
     
```

### String.prototype.repeat(numberOfTimes)

This method constructs and returns a new string which contains the specified number of copies of the string on which it was called, concatenated together.

``` js 

    let str = "Ha";
    console.log(str.repeat(3)); // Output: "HaHaHa"
    console.log(str.repeat("a")); // Output: ""
    console.log(str.repeat("")); // Output: ""
    
    console.log(str.repeat(true)); // Output: "Ha"
    console.log(str.repeat(false)); // Output: ""
    
```

### String.prototype.split(separatorString, limit)

The split() method turns a String into an array of strings, by separating the string at each instance of a specified separator string. It'll stop splitting when it the number of split operation performed is equal to the limit.

* If separator contains multiple characters, that entire character sequence must be found in order to split.

* If separator is omitted or does not occur in str, the returned array contains one element consisting of the entire string.

* If separator appears at the beginning or end of the string, or both, the array begins, ends, or both begins and ends, respectively, with an empty string.

* If separator is an empty string (""), str is converted to an array of each of its UTF-16 "characters".

* The array may contain fewer entries than limit if the end of the string is reached before the limit is reached.

* If limit is 0, no splitting is performed.

``` js 
    let str = "Miles to go before I sleep";
    
    console.log( str.split(" ") ); //Output: ["Miles", "to", "go", "before", "I", "sleep"]
    console.log( str.split("to") ); //Output: ["Miles ", " go before I sleep"]

    console.log( str.split("") ); // Output: ["M", "i", "l", "e", "s", " ", "t", "o", " ", "g", "o", " ", "b",                                             "e", "f", "o", "r", "e", " ", "I", " ", "s", "l", "e", "e", "p"]
    console.log(str.split("", 5)) // Output: ["M", "i", "l", "e", "s"]


```



### String.prototype.trim()

This method removes spaces from the beginning and end of the string.

``` js 

    let str = "     AltCampus      ";
    console.log(str.trim()); // Output: "AltCampus"
    
```

### String.prototype.trim()

This method removes spaces from the beginning and end of the string.

``` js 

    let str = "     AltCampus      ";
    console.log(str.trim()); // Output: "AltCampus"
    
```

### String.prototype.trimStart()

This method removes spaces from the beginning of the string.

``` js 

    let str = "     AltCampus      ";
    console.log(str.trimStart()); // Output: "AltCampus      "
    
```

### String.prototype.trimEnd()

This method removes spaces from the end of the string.

``` js 

    let str = "     AltCampus      ";
    console.log(str.trimEnd()); // Output: "     AltCampus"
    
```












